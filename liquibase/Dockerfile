FROM liquibase/liquibase:latest

# Download Oracle JDBC driver from Maven Central
RUN cd /liquibase/lib && \
    curl -L -o ojdbc11.jar https://repo1.maven.org/maven2/com/oracle/database/jdbc/ojdbc11/23.1.0.1/ojdbc11-23.1.0.1.jar

