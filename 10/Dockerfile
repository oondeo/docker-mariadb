
FROM oondeo/alpine

ENV SUMMARY="Mariadb (MYSQL) Image"	\
    DESCRIPTION="Mariadb (MYSQL) Image. The image use scripts and configurations compatible \
        with redhat openshift."

LABEL summary="$SUMMARY" \
      description="$DESCRIPTION" \
      io.k8s.description="$DESCRIPTION" \
      io.k8s.display-name="mariadb" \
      io.openshift.s2i.scripts-url=image:///usr/libexec/s2i/bin \
      io.s2i.scripts-url=image:///usr/libexec/s2i/bin \
      com.redhat.component="core" \
      name="oondeo/mariadb" \
      version="10" \
      release="2" \
      maintainer="OONDEO <info@oondeo.es>"

RUN apk-install mariadb mariadb-server-utils mariadb-backup mariadb-client \
    && rm -rf /etc/mysql && ln -s $HOME/../etc /etc/mysql \
    && mkdir -p $HOME/../mysql && ln -s $HOME/../mysql /var/lib/mysql 

COPY etc $HOME/../etc  
COPY s2i/bin $STI_SCRIPTS_PATH

RUN /usr/bin/docker-footer

EXPOSE 3306 

USER 1001

CMD [ "$STI_SCRIPTS_PATH/run" ]
