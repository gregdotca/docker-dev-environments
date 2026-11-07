FROM php:8.2.35-apache
ENV LOCALE1a="en_CA.UTF-8"
ENV LOCALE1b="en_CA:en"
ENV LOCALE2="en_US.UTF-8"
ENV LOCALE3="de_DE.UTF-8"
ENV LOCALE4="es_ES.UTF-8"
ENV LOCALE5="fr_FR.UTF-8"
ENV LOCALE6="it_IT.UTF-8"
ENV LOCALE7="nl_NL.UTF-8"
ENV LOCALE8="pl_PL.UTF-8"
ENV LOCALE9="pt_PT.UTF-8"
ENV LOCALE10="ru_RU.UTF-8"
ENV LOCALE11="ar_SA.UTF-8"
ENV LOCALE12="bn_BD UTF-8"
ENV LOCALE13="zh_CN.UTF-8"
ENV LOCALE14="zh_TW.UTF-8"
ENV LOCALE15="hi_IN UTF-8"
ENV LOCALE16="id_ID.UTF-8"
ENV LOCALE17="ja_JP.UTF-8"
ENV LOCALE18="ko_KR.UTF-8"
ENV LOCALE19="mr_IN UTF-8"
ENV LOCALE20="fa_IR UTF-8"
ENV LOCALE21="pt_BR.UTF-8"
ENV LOCALE22="ta_IN UTF-8"
ENV LOCALE23="te_IN UTF-8"
ENV LOCALE24="tr_TR.UTF-8"
ENV LOCALE25="ur_PK UTF-8"
ENV LOCALE26="vi_VN UTF-8"

RUN echo "ServerName localhost" >> /etc/apache2/apache2.conf
RUN apt-get update \
#    && apt-get install -y bzip2 cron git gzip tar \
#    && apt-get install -y curl gettext libxml2 libxml2-dev locales mlocate tzdata vim php-xdebug \
    && apt-get install -y curl gettext libxml2 libxml2-dev locales plocate tzdata vim \
    && apt-get clean -y \
#    && docker-php-ext-install intl mbstring
    && docker-php-ext-install gettext mysqli pdo pdo_mysql simplexml
#RUN apt-get update \
#    && apt-get install -y gettext \
#    && apt-get clean -y \
#    && docker-php-ext-install gettext
COPY php.ini-development /usr/local/etc/php/php.ini
RUN sed -i -e "s/# $LOCALE1a/$LOCALE1a/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE2/$LOCALE2/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE3/$LOCALE3/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE4/$LOCALE4/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE5/$LOCALE5/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE6/$LOCALE6/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE7/$LOCALE7/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE8/$LOCALE8/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE9/$LOCALE9/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE10/$LOCALE10/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE11/$LOCALE11/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE12/$LOCALE12/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE13/$LOCALE13/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE14/$LOCALE14/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE15/$LOCALE15/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE16/$LOCALE16/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE17/$LOCALE17/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE18/$LOCALE18/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE19/$LOCALE19/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE20/$LOCALE20/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE21/$LOCALE21/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE22/$LOCALE22/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE23/$LOCALE23/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE24/$LOCALE24/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE25/$LOCALE25/" /etc/locale.gen
RUN sed -i -e "s/# $LOCALE26/$LOCALE26/" /etc/locale.gen
RUN locale-gen
RUN echo "LANG=$LOCALE1a" > /etc/default/locale
ENV LANG $LOCALE1a
ENV LC_ALL $LOCALE1a
RUN a2enmod rewrite
RUN service apache2 restart
RUN mkdir -p /var/www/html/domainmod/temp
# RUN chmod -R 777 /var/www/html/domainmod/temp
RUN chmod 777 /var/www/html/domainmod/temp
RUN touch /tmp/domainmod.log
RUN chmod 777 /tmp/domainmod.log
EXPOSE 80
