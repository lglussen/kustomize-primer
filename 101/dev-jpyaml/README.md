# JSON Patch as YAML

Kustomize will accept a yaml string input as a [JSON Patch](https://jsonpatch.com).

The important consideration is the block of yaml is a string and not just a nested
chunk of yaml under the `patch`.  The use of the `|` operator after the 'pactc: ' key
instructs the yaml interpreter to read the following block as a multiline string rather
than a continuation of the yaml data-strucure.


