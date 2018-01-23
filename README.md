# Kubernetes scripts

This repository contains some useful scripts for operating Kubernetes.

- `create-kubeconfig`: Create a kubeconfig to access the apiserver with the specified serviceaccount and outputs it to stdout.
- `wait-until-pods-ready`: Wait for all pods to be ready in the current namespace.
- `force-update-deployment`: Recreate the pods managed by the specified deployment.
- `apiversion2resources`: Convert API versions read from STDIN to resources in the form of `apiversion.resource`.

## How to use

**apiversion2resources**

```
# Convert the supported API versions on the server
$ kubectl api-versions | apiversion2resources
```

## License

These scripts are released under the MIT License.
