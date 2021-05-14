FROM mcr.microsoft.com/azure-sql-edge:latest

ENV SA_PASSWORD <strongPassword>
ENV ACCEPT_EULA Y
ENV MSSQL_PID Developer
EXPOSE 1433

USER root

COPY ./Scripts/Initialize.sql .
COPY ./Scripts/Databases .
COPY ./Scripts/Tables .

RUN /opt/mssql/bin/sqlservr --accept-eula & sleep 23 \
    && /opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P $SA_PASSWORD -i Initialize.sql \
    && pkill sqlservr