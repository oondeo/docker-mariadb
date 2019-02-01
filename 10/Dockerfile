
FROM quay.io/oondeo/alpine
ARG MARIADB_VERSION="10.2.19-r1"

ENV SUMMARY="Mariadb (MYSQL) Image"	\
    DESCRIPTION="Mariadb (MYSQL) Image. The image use scripts and configurations compatible \
        with redhat openshift."

LABEL summary="$SUMMARY" \
      description="$DESCRIPTION" \
      io.k8s.description="$DESCRIPTION" \
      io.k8s.display-name="mariadb" \
      io.openshift.expose-services="3306:mysql" \
      io.openshift.tags="database,mysql,mariadb,mariadb102,mariadb-102" \
      com.redhat.component="mariadb" \
      name="oondeo/mariadb" \
      version="${MARIADB_VERSION}" \
      release="1" \
      maintainer="OONDEO <info@oondeo.es>"

RUN mkdir -p $HOME/../mysql && ln -s $HOME/../mysql /var/lib/mysql \
    && apk-install mariadb mariadb-server-utils mariadb-backup mariadb-client \
    && rm -rf /etc/mysql && ln -s $HOME/../etc /etc/mysql  

COPY etc $HOME/../etc  
COPY s2i/bin $STI_SCRIPTS_PATH

RUN /usr/bin/docker-footer

EXPOSE 3306 

USER 1001

CMD [ "$STI_SCRIPTS_PATH/run" ]
