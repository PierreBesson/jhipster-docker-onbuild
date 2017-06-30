FROM maven:3-jdk-8

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app
ONBUILD ADD . /usr/src/app

# Build from sources
ONBUILD RUN echo '{ "allow_root": true }' > /root/.bowerrc && \
    rm -Rf node_modules && \
    ./mvnw clean package -Pprod -DskipTests && \
    mv target/*.war /app.war
#   TODO for gradle
#     ./gradlew -Pprod build -x test && \
#     mv /home/jhipster/github/build/libs/*.war /app.war && \
ENV JHIPSTER_SLEEP 0

ONBUILD RUN sh -c 'touch /app.war'
EXPOSE 8080
ONBUILD CMD echo "The application will start in ${JHIPSTER_SLEEP}s..." && \
    sleep ${JHIPSTER_SLEEP} && \
    java -Djava.security.egd=file:/dev/./urandom -jar /app.war
