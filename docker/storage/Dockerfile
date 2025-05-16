FROM alpine:3.21 AS build

WORKDIR /app

COPY ./bin/storage-service ./storage-service

RUN chmod +x ./storage-service

FROM scratch

WORKDIR /app

COPY --from=build /app/storage-service ./storage-service

EXPOSE 80

ENTRYPOINT [ "/app/storage-service" ]
