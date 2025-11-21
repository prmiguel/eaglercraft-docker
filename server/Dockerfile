FROM nginx:alpine AS repository
ARG EAGLERCRAFT_SERVER_URL=https://github.com/Eaglercraft-Templates/Eaglercraft-Server-Paper.git
WORKDIR /repository
RUN apk add git && \
    git clone $EAGLERCRAFT_SERVER_URL

FROM eclipse-temurin:17-jdk
WORKDIR /source
COPY --from=repository /repository/Eaglercraft-Server-Paper /source
RUN chmod +x /source/run.sh
EXPOSE 25565
CMD ["/source/run.sh"]
