FROM nginx:alpine AS downloader
ARG EAGLERCRAFT_CLIENT_URL=https://bafybeihn2tdt55pg5hvju7zu4jkp7mglu3ynisgzmqm7ebkec4qi7lgt4y.ipfs.dweb.link/?filename=EaglercraftX_1.8_Signed_Offline.zip
WORKDIR /downloader
RUN apk add wget unzip && \
    wget -O eaglercraft.zip $EAGLERCRAFT_CLIENT_URL && \
    unzip eaglercraft.zip && rm *.zip && \
    mv *.html index.html

FROM nginx:alpine
COPY --from=downloader /downloader /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
