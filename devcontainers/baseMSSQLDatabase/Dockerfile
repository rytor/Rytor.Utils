FROM mcr.microsoft.com/mssql/server:2019-latest

# Set the environment variables
ENV ACCEPT_EULA=Y
ENV SA_PASSWORD=$SQL_PASSWORD

# Expose the port for SQL Server
EXPOSE 1433

# Copy the database scripts to the container
#COPY ./scripts /scripts

# Grant permissions for the scripts
#RUN chmod +x /scripts/*.sh

# Run the scripts when the container starts
#ENTRYPOINT /bin/bash /scripts/entrypoint.sh