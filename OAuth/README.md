## Configuration assumes secret/ldap-secret exists 
oc create secret generic ldap-secret --from-literal=bindPassword=<secret> -n openshift-config
