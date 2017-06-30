FROM jhipster/jhipster:onbuild

FROM openjdk:8-jre-alpine
COPY --from=0 /app.war /

ENV JHIPSTER_SLEEP 0
EXPOSE 8080
CMD echo "The application will start in ${JHIPSTER_SLEEP}s..." && \
    sleep ${JHIPSTER_SLEEP} && \
    java -Djava.security.egd=file:/dev/./urandom -jar /app.war
