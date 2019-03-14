
FROM oondeo/alpine:3.9
ARG MARIADB_VERSION="10.3.13"

ENV SUMMARY="Mariadb (MYSQL) Image"	\
    DESCRIPTION="Mariadb (MYSQL) Image. The image use scripts and configurations compatible \
        with redhat openshift."

LABEL summary="$SUMMARY" \
      description="$DESCRIPTION" \
      io.k8s.description="$DESCRIPTION" \
      io.k8s.display-name="mariadb" \
      io.openshift.expose-services="3306:mysql" \
      io.openshift.tags="database,mysql,mariadb,mariadb102,mariadb-103" \
      com.redhat.component="mariadb" \
      name="oondeo/mariadb" \
      version="${MARIADB_VERSION}" \
      release="1" \
      maintainer="OONDEO <info@oondeo.es>"

USER root

RUN mkdir -p $HOME/../mysql/data && ln -s $HOME/../mysql/data /var/lib/mysql \
    && mkdir -p $HOME/../docker-entrypoint-initdb.d && ln -s $HOME/../docker-entrypoint-initdb.d /docker-entrypoint-initdb.d \
    && mkdir /run/mysqld && chown 1001 /run/mysqld && chmod 770 /run/mysqld \
    && apk-install mariadb mariadb-server-utils mariadb-backup mariadb-client pwgen tzdata \
    && rm -rf /etc/mysql /etc/my.cnf* && ln -s $HOME/../etc /etc/mysql && ln -s $HOME/../etc/my.cnf /etc/my.cnf

COPY etc $HOME/../etc  
COPY s2i/bin $STI_SCRIPTS_PATH
COPY mariadb-sys /usr/share/mariadb-sys

ENV DATADIR=/opt/app-root/mysql/data

RUN /usr/bin/docker-footer

EXPOSE 3306 

USER 1001

CMD [ "run","mysqld" ]
