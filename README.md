Kitchensink on OpenShift
=========================

This is the kitchensink JBoss quickstart app.  You can find more info @ http://www.jboss.org/jdf/quickstarts/jboss-as-quickstart/guide/KitchensinkQuickstart/

Running on OpenShift Online
--------------------

Create an account at https://www.openshift.com

Create a jbossas-7 application

    rhc app create kitchensink jbossas-7 --from-code http://gitlab.osecloud.com/jenkins/kitchensink.git

That's it, you can now checkout your application at:

    http://kitchensink-$namespace.rhcloud.com

PostgreSQL as a backend
-----------------------
By default, this quickstart uses H2 as the backend, but you may use
PostgreSQL.

To do this, add PostgreSQL cartridge to your application:

    rhc cartridge add postgresql-8.4 -a kitchensink

Edit `src/main/resources/META-INF/persistence.xml` so that the data
source points to `java:jboss/datasources/PostgreSQLDS`:

    <jta-data-source>java:jboss/datasources/PostgreSQLDS</jta-data-source>

Commit this change, and push.
