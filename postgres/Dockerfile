FROM curlimages/curl AS builder
RUN curl -sSf https://raw.githubusercontent.com/OpenOLAT/OpenOLAT/refs/tags/OpenOLAT_20.0.3/src/main/resources/database/postgresql/setupDatabase.sql -o /tmp/setupDatabase.sql

FROM postgres:9
COPY --from=builder /tmp/setupDatabase.sql /docker-entrypoint-initdb.d/setupDatabase.sql
