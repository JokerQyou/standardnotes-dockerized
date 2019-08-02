FROM node:8-stretch-slim as builder
WORKDIR /
RUN npm install --save standard-notes-web && \
    cd /node_modules/standard-notes-web && \
    rm -rf README.md LICENSE package.json docker Dockerfile log && \
    cd public/extensions && \
    rm -rf batch-manager/app extension-manager/app && \
    cd /node_modules && \
    find -type f \( -name "README.md" \
                    -o -name ".*" \
                    -o -name "webpack.config.js" \
                    -o -name "yarn.lock" \
                    -o -name "*.map" \) | xargs rm && \
    cd / && \
    wget https://github.com/weihanglo/sfz/releases/download/0.0.3/sfz-0.0.3-x86_64-unknown-linux-musl.tar.gz -O sfz.tar.gz && \
    tar xf sfz.tar.gz && \
    rm sfz.tar.gz

FROM scratch
WORKDIR /
COPY --from=builder /node_modules/standard-notes-web/ /
COPY --from=builder /sfz /

ENTRYPOINT [ "/sfz" ]
