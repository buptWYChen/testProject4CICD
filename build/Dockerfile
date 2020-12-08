FROM maven as builder
WORKDIR /work/
COPY  . .
COPY settings.xml /root/.m2/settings.xml
RUN  mvn clean install  -DskipTests
RUN  ls target


FROM java:8
WORKDIR /app/
COPY --from=builder /work/target/helloworld.jar .
EXPOSE 8081
CMD ["java","-jar","/app/atms-back-1.0.jar"]
