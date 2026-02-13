FROM liquibase/liquibase:latest

# Install curl and ca-certificates
RUN apt-get update && apt-get install -y curl ca-certificates && rm -rf /var/lib/apt/lists/*

# Download Oracle JDBC driver from Maven Central
RUN cd /liquibase/lib && \
    echo "Downloading Oracle JDBC driver..." && \
    curl -L -f -o ojdbc11.jar https://repo1.maven.org/maven2/com/oracle/database/jdbc/ojdbc11/23.1.0.1/ojdbc11-23.1.0.1.jar && \
    ls -lh ojdbc11.jar && \
    echo "Oracle JDBC driver downloaded successfully"

