FROM adoptopenjdk/openjdk11:alpine-jre

LABEL maintainer="Anoop Nair"

# Add the dependencies as a separate layer
COPY target/thin/root/repository /opt/anair/repository

# Add the app as a thin layer
COPY  target/thin/root/anair-fn.jar /opt/anair/app.jar

ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/opt/anair/app.jar", "--thin.root=/opt/anair/."]
