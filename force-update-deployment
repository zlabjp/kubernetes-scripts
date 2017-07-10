#!/usr/bin/env bash

# Copyright 2017, Z Lab Corporation. All rights reserved.
# Copyright 2017, Kubernetes scripts contributors
#
# For the full copyright and license information, please view the LICENSE
# file that was distributed with this source code.

set -e

if [[ $# == 0 ]]; then
  echo "Usage: $0 DEPLOYMENT [kubectl options]" >&2
  echo "" >&2
  echo "This script recreates the pods managed by the specified deployment." >&2
  exit 1
fi

function _kubectl() {
  kubectl $@ $kubectl_options
}

deployment="$1"
updated_at=$(date +%s)
kubectl_options="${@:2}"

_kubectl patch deployment "$deployment" \
  -p "{\"spec\":{\"template\":{\"metadata\":{\"annotations\":{\"force-update.zlab.co.jp/updated-at\":\"$updated_at\"}}}}}"
