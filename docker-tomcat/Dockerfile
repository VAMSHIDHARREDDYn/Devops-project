FROM tomcat:latest

# Copy webapps from dist to webapps (newer Tomcat images have empty webapps by default)
RUN cp -r /usr/local/tomcat/webapps.dist/* /usr/local/tomcat/webapps/

# Copy custom index.html to ROOT
COPY index.html /usr/local/tomcat/webapps/ROOT/index.html

# Update context.xml to allow all IPs for manager access
RUN sed -i 's/allow="127\\.\\d+\\.\\d+\\.\\d+|::1|0:0:0:0:0:0:0:1"/allow=".*"/g' \
    /usr/local/tomcat/webapps/manager/META-INF/context.xml && \
    sed -i 's/allow="127\\.\\d+\\.\\d+\\.\\d+|::1|0:0:0:0:0:0:0:1"/allow=".*"/g' \
    /usr/local/tomcat/webapps/host-manager/META-INF/context.xml

# Copy custom tomcat-users.xml
COPY tomcat-users.xml /usr/local/tomcat/conf/tomcat-users.xml

EXPOSE 8080
