# Stratigic Merge with External Patch File

[kustomization docs](https://kubernetes.io/docs/tasks/manage-kubernetes-objects/kustomization/)

Stratigic Merge uses the provided "shim" object to idetify the patch target(s) and merges what is defined into
the existing obeject. This works well for dictionary edits and less so for arrays of literal values.

External patch files may use the yaml `---` document separator to place multiple patches in the same file.

