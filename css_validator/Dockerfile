FROM tomcat:8.0-jre7-alpine

ENV PATH="${PATH}:/usr/local/tomcat/apache-ant-1.9.9/bin" 

RUN apk add --no-cache git openjdk7 wget tar \
    && git clone https://github.com/w3c/css-validator \
    && wget --quiet http://mirror.nbtelecom.com.br/apache//ant/binaries/apache-ant-1.9.9-bin.tar.gz \
    && tar -xzf apache-ant-1.9.9-bin.tar.gz \
    && rm apache-ant-1.9.9-bin.tar.gz \
    && cd css-validator \
    && ant war \
    && rm -fr /usr/local/tomcat/webapps/ROOT \
    && mv /usr/local/tomcat/css-validator/css-validator.war /usr/local/tomcat/webapps/ROOT.war \
    && rm -fr /usr/local/tomcat/apache-ant-1.9.9 \
    && rm -fr /usr/local/tomcat/css-validator \
    && apk del git openjdk7 wget tar 

CMD ["catalina.sh", "run"]



