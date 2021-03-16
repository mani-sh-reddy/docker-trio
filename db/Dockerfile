# Derived from official mysql image (our base image)
# Use mysql 5.7 as the flask-app is not set up to work with later versions
FROM mysql:5.7
# Add a database and root password
# For hints on how to do this, consult the mysql 5.7 image documentation
ARG MYSQL_DATABASE=$MYSQL_DATABASE
ARG MYSQL_ROOT_PASSWORD=$MYSQL_ROOT_PASSWORD
# Add the content of the .sql file to your image
RUN mysql CreateTable.sql
# All scripts copied to docker-entrypoint-initdb.d/ are automatically
COPY . docker-entrypoint-initdb.d/
# executed during container startup
ENTRYPOINT ["docker-entrypoint-initdb.d/"]
