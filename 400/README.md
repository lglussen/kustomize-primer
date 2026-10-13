# Utilizing Helm Templates

One of the biggest limitations of Kustomize is the inability to use variables
and the inability to construct a variable number of objects.

While most infrastructure configuration involves fixed configuration object and
is perfectly suited for Kustomize, sometimes a more dynamic approach is
needed to solve an issue.

Fortunately, Kustomize supports calling Helm Charts which means we don't need to
pick between a Helm Templating approach and a Kustomize overlay approach.
Instead, we can default to using Kustomize with the understanding that it
will cover the majority of our use cases without limiting our ability to dip
into templating if it proves necessary for a task.

## Understanding the example

This example has the administrator creating a number of "sandbox" namespaces based on
a variable list of users.


