# Basic Dev/Test/Prod example

This project creates a simple deployment and highlights how kustomize supports

## Explore the config

`base` contains the basic configuration to create a deployment while each
respective environment adds a unique configmap to inject environment specific data.

Note in this example we are not patching at all - instead choosing to introduce
the ConfigMap at the respective environment directory. Patching a ConfigMap
defined in the base config would have been a valid strategy - it is simply a
choice made base on the simplicity of the object and lake of any shared config values.

## Apply the config

Until now, we have been running `oc kustomize .` to generate the content.
A valid approach would be:

```shell
oc kustomize . | oc apply -f -
```

However, we can be more succinct with `oc apply -k .`
```shell
# test with --dry-run
oc apply -k . --dry-run

# apply the changes
oc apply -k .
```

## Modify the config

1. Change the value in the ConfigMap
2. Verify what will be changed
   ```shell
   oc diff -k .
   ```
3. Apply the changes
   ```shell
   oc apply -k .
   ```
4. Validate the change to the application by viewing the route in a browser
5. Realize the configmap value change didn't rollout a new deployment
6. Understand Kustomize has solutions for ConfigMap and Secret changes
   - configMapGenerator
   - secretGenerator
7. For now, lets just force the refresh
   ```shell
   oc delete -k .
   oc apply -k .
   ```

## Apply for different environment

Change directory from `dev` to `test` or `prod`. 

```shell
oc delete -k .
oc apply -k .
```

Understand that the intent is for a GitOps tool such as ArgoCD.
The tool would map a particular cluster to a `(branch/tag)+directory` of the Git repository.
 
