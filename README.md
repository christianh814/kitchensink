Kitchensink on OpenShift
=========================

This is the kitchensink JBoss quickstart app.  You can find more info [here](http://www.jboss.org/jdf/quickstarts/jboss-as-quickstart/guide/KitchensinkQuickstart/)

Running on OpenShift
--------------------

Create The application using the template and editing your values (note your APPLICATION_HOSTNAME will be different depending on where you're logged in to):

```
oc new-app --template=eap6-basic-sti -p APPLICATION_NAME=ks,APPLICATION_HOSTNAME=ks-chx.apps.osecloud.com,GIT_URI=https://github.com/RedHatWorkshops/kitchensink,GIT_REF="",GIT_CONTEXT_DIR=""
```

View your build

    oc get builds
    oc build-logs ks-1

Visit your application
```
firefox ks-chx.apps.osecloud.com
```
