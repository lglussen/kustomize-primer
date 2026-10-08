## Explore the base config

- notice how the kustomization.yaml file includes resources
- run `oc kustomize .` from the `base` directory and notice the output

## JSON Patch

- Explore the `dev-jp` kustomization.yaml and notice how JSON Patch is used to apply a patch
- run `oc kustomize .` from `dev-jp` view the effect of the patch


## JSON Patch as YAML 

- Explore the `dev-jpyaml` kustomization.yaml and notice how JSON Patch can be written in yaml format
- run `oc kustomize .` from `dev-jp` view the effect of the patch

## Strategic Merge Patch

- Explore the `dev-sm-inline` kustomization.yaml and notice how a Strategic Merge can be applied inline
- Explore the `dev-sm` kustomization.yaml and notice how a Strategic Merge can be applied with external patch files

## Mix and Match

Explore the `dev-all` kustomization.yaml and notice how all patch techniques may be used

## Include additional content

Explore the `prod` kustomization.yaml and notice how it is adding additional content on top of what is pulled from `../base`

