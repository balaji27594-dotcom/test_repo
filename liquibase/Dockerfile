FROM eclipse-temurin:21-jre

# Install Liquibase and dependencies
RUN apt-get update && \
    apt-get install -y curl unzip && \
    rm -rf /var/lib/apt/lists/*

# Install Liquibase
RUN mkdir -p /liquibase && \
    cd /liquibase && \
    curl -L -o liquibase.tar.gz https://github.com/liquibase/liquibase/releases/download/v5.0.1/liquibase-5.0.1.tar.gz && \
    tar xzf liquibase.tar.gz && \
    rm liquibase.tar.gz && \
    chmod +x /liquibase/liquibase

# Download Oracle JDBC driver to lib directory
RUN mkdir -p /liquibase/lib && \
    cd /liquibase/lib && \
    echo "Downloading Oracle JDBC driver..." && \
    curl -L -f -o ojdbc11.jar https://repo1.maven.org/maven2/com/oracle/database/jdbc/ojdbc11/23.1.0.1/ojdbc11-23.1.0.1.jar && \
    ls -lh ojdbc11.jar && \
    echo "Oracle JDBC driver downloaded successfully"

# Set working directory
WORKDIR /liquibase

# Add liquibase to PATH
ENV PATH="/liquibase:${PATH}"

ENTRYPOINT ["/liquibase/liquibase"]

