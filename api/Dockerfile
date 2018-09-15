FROM maven:3.3-jdk-8 as build

WORKDIR /usr/src/mymaven
COPY . ./
RUN mvn -B -f pom.xml -s /usr/share/maven/ref/settings-docker.xml dependency:resolve \
    && mvn -B -s /usr/share/maven/ref/settings-docker.xml package -DskipTests


FROM java:8-jre-alpine
COPY --from=build /usr/src/mymaven/target/ddev-0.0.1-SNAPSHOT.jar .
RUN adduser -Dh /home/gordon gordon
CMD java -jar ./ddev-0.0.1-SNAPSHOT.jar \
    --spring.profiles.active=postgres
