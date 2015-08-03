Kitchensink on OpenShift
=========================

This is the kitchensink JBoss quickstart app.  You can find more info [here](http://www.jboss.org/jdf/quickstarts/jboss-as-quickstart/guide/KitchensinkQuickstart/)

Running on OpenShift
--------------------

Clone the OpenShift 3 templates
```
git clone https://github.com/openshift/openshift-ansible
```

Make sure you're in the right directory

    cd openshift-ansible/roles/openshift_examples/files/examples/xpaas-templates/

Create The application using the template and editing your values (note your APPLICATION_HOSTNAME will be different depending on where you're logged in to):

    oc process -f eap6-basic-sti.json -v APPLICATION_NAME=ks,APPLICATION_HOSTNAME=ks.demo.sbx.osecloud.com,GIT_URI=https://github.com/christianh814/kitchensink,GIT_REF="",GIT_CONTEXT_DIR="" | oc create -f -

View your build

    oc get builds
    oc build-logs ks-1

Visit your application
```
firefox http://ks.demo.sbx.osecloud.com
```
