# Basic Dev/Test/Prod example + configMapGenerator

This example shows how a `configMapGenerator` can be used to solve the issue
of deployments not automatically updating when the contents relevant ConfigMaps
are updated.

A configMapGenerator generates a unique name for the configmap and replaces all
references to the 'static' name with the generated name. The generated name only
changes if the contents of the ConfigMap are changed.

In this way, changes to the ConfigMap contents create a change to the content of the
Deployment object by changing the name of the referenced ConfigMap. Therefore, a
change to the contents of the ConfigMap will trigger a new deployment and our new
ConfigMap content will be reflected by the running application.

