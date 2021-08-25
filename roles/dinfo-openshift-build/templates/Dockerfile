# https://hub.docker.com/_/httpd
FROM httpd:buster   

# Install all Perl dependencies with XS code out of the distribution,
# so that we don't have to deal with development kits
RUN set -e -x; \
    export DEBIAN_FRONTEND=noninteractive ; \
    apt-get update ; \
    apt-get install -y \
        cpanminus \
        default-mysql-client \
        libdbd-mysql-perl \
        libdigest-sha-perl \
        libio-socket-ssl-perl \
        libjson-perl \
        libnet-ldap-perl \
        libnet-ssleay-perl \
        libperlio-utf8-strict-perl \
        make \
        vim ; \
    apt-get -y clean

# Install Perl dependencies out of CPAN (except those that link to C code,
# that should have been installed out of the distro, above)
COPY cpanfile cpanfile
RUN cpanm --installdeps --notest .

# Enable apache modules. `headers` and `env` modules are enabled by default.
RUN sed -i \
    -e 's/^#\(LoadModule .*mod_rewrite.so\)/\1/' \
    -e 's/^\s#\(LoadModule .*mod_cgid\?.so\)/\1/' \
    -e 's/^#\(LoadModule .*mod_remoteip.so\)/\1/' \
    /usr/local/apache2/conf/httpd.conf
