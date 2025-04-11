# gitopsexample
example of how to manage multiple VMs with GitOps

## prepare cluster
```
namespace=exampleproject
oc new-project $namespace
oc label namespace $namespace argocd.argoproj.io/managed-by=openshift-gitops
```

## single application
`argo/singleapplication.yaml` is an example of how to manage a number of VMs by a single Argo application. The application will be out of sync as soon as any VM is out of sync.

## applicationset
`argo/applicationset.yaml` is an example of how to manage each VM (or related VMs) by a dedicated Argo application using a [git generator](https://argo-cd.readthedocs.io/en/stable/operator-manual/applicationset/Generators/).
