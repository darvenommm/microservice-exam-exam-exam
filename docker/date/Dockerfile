FROM alpine:3.21 AS build

WORKDIR /app

COPY ./bin/date-service ./date-service

RUN chmod +x ./date-service

FROM scratch

WORKDIR /app

COPY --from=build /app/date-service ./date-service

EXPOSE 80

ENTRYPOINT [ "/app/date-service" ]
