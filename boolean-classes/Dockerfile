FROM nimmis/apache-php7

RUN mkdir -p /var/www/boolean-classes
RUN a2dissite 000-default
ADD boolean.conf /etc/apache2/sites-availalbe/
CMD ["a2ensite boolean"]

ENTRYPOINT service apache2 start
