Kitchensink on OpenShift
=========================

This is the kitchensink JBoss quickstart app.  You can find more info [here](http://www.jboss.org/jdf/quickstarts/jboss-as-quickstart/guide/KitchensinkQuickstart/)

Running on OpenShift
--------------------

Create a jbossas-7 application

    oc new-app jboss-eap6-openshift~https://github.com/christianh814/kitchensink --name=ks

Start your build:

    oc start-build ks

View the build if you with

    oc get builds
    oc build-logs ks-1

Create a route

    oc expose service ks
    
If you make a change to the code just fire off another build

    oc start-build ks
