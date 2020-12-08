FROM maven as builder
WORKDIR /work/
COPY ./helloworld/ .
COPY /helloworld/settings.xml /root/.m2/settings.xml
RUN  mvn clean install  -DskipTests
RUN  ls target


FROM java:8
WORKDIR /app/
COPY --from=builder /work/target/demo-0.0.1-SNAPSHOT.jar .
EXPOSE 8081
CMD ["java","-jar","/app/demo-0.0.1-SNAPSHOT.jar"]
