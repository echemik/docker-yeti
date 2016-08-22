FROM php:5.6-apache
# SugarCRM 7.21 MAX
ENV DOWNLOAD_URL https://github.com/YetiForceCompany/YetiForceCRM/archive/3.1.0.zip
ENV DOWNLOAD_FILE tmp2.zip
ENV EXTRACT_FOLDER YetiForceCRM-3.1.0
ENV WWW_FOLDER /var/www/html
ENV WWW_USER www-data
ENV WWW_GROUP www-data

RUN apt-get update
# Install unzip
RUN apt-get install -y unzip
# Install curl
RUN apt-get install -y curl wget
RUN cd /var/www/html/
RUN wget https://github.com/YetiForceCompany/YetiForceCRM/archive/3.1.0.zip
RUN unzip 3.1.0.zip
RUN rm 3.1.0.zip

RUN cp -R ${EXTRACT_FOLDER}/* ${WWW_FOLDER}/
RUN rm -R ${EXTRACT_FOLDER}
RUN chown -R ${WWW_USER}:${WWW_GROUP} ${WWW_FOLDER}/*
RUN chown -R ${WWW_USER}:${WWW_GROUP} ${WWW_FOLDER}

EXPOSE 80
