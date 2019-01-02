FROM xbdtb/maven:3.6.0-jdk-8-alpine-1 as builder
RUN mkdir /app
ADD . /app
WORKDIR /app
RUN mvn -Djar.finalName=app.jar install
RUN ls target

FROM openjdk:8-jre-alpine
RUN mkdir /app
WORKDIR /app
COPY --from=builder /app/target/app.jar .
CMD java -jar app.jar
