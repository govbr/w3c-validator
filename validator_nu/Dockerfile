FROM alpine:3.6

RUN apk --no-cache add openjdk8-jre unzip wget \
    && wget --quiet https://github.com/validator/validator/releases/download/17.9.0/vnu.jar_17.9.0.zip \
    && unzip vnu.jar_17.9.0.zip \
    && rm vnu.jar_17.9.0.zip \
    && mv dist/vnu.jar . \
    && rm -Rf dist \
    && apk del unzip wget

EXPOSE 8888
CMD ["java", "-cp", "./vnu.jar", "nu.validator.servlet.Main", "8888"]

