# OpenShift ActiveMQ client with CDI


### Start an ActiveMQ Broker

    oc new-project amq-demo

    oc policy add-role-to-user view system:serviceaccount:amq-demo:default

    oc process -f amq62-basic.json -v MQ_USERNAME=admin,MQ_PASSWORD=admin | oc create -f -

### Build the project

    mvn clean install -s configuration/settings.xml
    mvn -Pf8-local-deploy -s configuration/settings.xml

### More Examples
You can generate this project using the following archetype
https://access.redhat.com/documentation/en/red-hat-xpaas/version-0/red-hat-xpaas-a-mq-image/#example_deployment_workflow

 * JBoss Fuse repository: https://repo.fusesource.com/nexus/content/groups/public/
 * RedHat GA repository: https://maven.repository.redhat.com/ga

    mvn archetype:generate \
      -DarchetypeCatalog=https://repo.fusesource.com/nexus/content/groups/public/archetype-catalog.xml \
      -DarchetypeGroupId=io.fabric8.archetypes \
      -DarchetypeVersion=2.2.0.redhat-079 \
      -DarchetypeArtifactId=cdi-camel-mq-archetype


More examples

    mvn archetype:generate \
      -DarchetypeCatalog=https://repo.fusesource.com/nexus/content/groups/public/archetype-catalog.xml \
      -DarchetypeGroupId=io.fabric8.archetypes \
      -DarchetypeVersion=2.2.0.redhat-079 \
      -DarchetypeArtifactId=cdi-camel-jetty-archetype

    mvn clean install
    mvn -Pf8-local-deploy

http://qs-cdi-camel-jetty-bilgin.rhel-cdk.10.1.2.2.xip.io/camel/hello?name=donald




