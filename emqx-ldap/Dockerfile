FROM osixia/openldap:1.2.2

RUN apt-get update -y \
    && apt-get install -y git \
    && git clone https://github.com/emqx/emqx-auth-ldap.git /tmp/emqx_auth_ldap \
    && mkdir -p /container/service/slapd/config/bootstrap/ldif \
    && cp /tmp/emqx_auth_ldap/emqtt.com.ldif /container/service/slapd/config/bootstrap/ldif/50-bootstrap.ldif \
    && cp /tmp/emqx_auth_ldap/emqtt.schema /container/service/slapd/assets/config/bootstrap/schema/emqtt.schema 
