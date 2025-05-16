FROM alpine:3.21 AS build

WORKDIR /app

COPY ./bin/core-service ./core-service

RUN chmod +x ./core-service

FROM scratch

WORKDIR /app

COPY --from=build /app/core-service ./core-service

EXPOSE 80

ENTRYPOINT [ "/app/core-service" ]
