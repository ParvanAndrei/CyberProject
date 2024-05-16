# Use the official Apache image as base
FROM httpd:2.4-buster

# Copy custom Apache configuration files
# COPY ./apache-proxy/httpd.conf /usr/local/apache2/conf/httpd.conf
COPY ./httpd.conf /usr/local/apache2/conf/httpd.conf
# COPY ./apache-proxy/auth_openidc.conf /usr/local/apache2/conf/auth_openidc.conf
COPY ./auth_openidc.conf /usr/local/apache2/conf/auth_openidc.conf
# COPY ./apache-proxy/httpd-vhosts.conf /usr/local/apache2/conf/extra/httpd-vhosts.conf
COPY ./httpd-vhosts.conf /usr/local/apache2/conf/extra/httpd-vhosts.conf

# Install mod_auth_openidc and any other required packages
RUN apt-get update && \
    apt-get install -y libapache2-mod-auth-openidc net-tools

# Start Apache in the foreground
CMD ["httpd", "-D", "FOREGROUND"]
