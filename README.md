#сначала надо обновить ОС
```
apt-get update -y 
```
но на Debian 7 в конце возникает такая ошибка (на Debian 8 ошибки нету, но некоторые знатоки пишут, что она типа еще сырая для сервера)  
Зато на Debian 8 по умолчанию ставится php 5.6, а на Debian 7 по умолчанию 5.4. И чтобы поставить 5.6 надо нормально заморочиться.
```
W: There is no public key available for the following key IDs:
7638D0442B90D010
W: There is no public key available for the following key IDs:
9D6D8F6BC857C906
```
лечится это так
```
apt-get install debian-keyring debian-archive-keyring
apt-get install
```

теперь можно попробовать еще раз и убедиться, что ошибки больше нет
```
apt-get update && apt-get upgrade
```

#потом ставим разные полезные утилиты
```
apt-get install mc nano vsftpd zip unzip -y    
```

#далее ставим компоненты веб-сервера (кроме nginx, т.к. я с ним пока не разобрался)
```
apt-get install apache2 php5 libapache2-mod-php5 php5-fpm mysql-server mysql-client php5-mysql  php5-curl  curl phpmyadmin git imagemagick -y
```
когда phpMyAdmin спросит *Выберите веб-сервер, который будет автоматически настроен для запуска phpMyAdmin.*  
Веб-сервер для автоматической перенастройки:  
[] apache2     - Выбираем именно apache2!  
потом на вопрос **configure database for phpmyadmin with dbconfig-common** отвечаем нет  

#Для Laravel нужен composer!  
установка композера глобально (это composer-wrap вместо стандартного композера, который позволяет устанавливать пакеты типа laravel глобально для всех пользователей, а не только для root)
```
git clone https://github.com/mekras/composer-wrap
mv composer-wrap/composer /usr/local/bin/composer
rm -r composer-wrap
composer
```

#устанавливаем laravel installer globally
```
composer global require "laravel/installer"
```

#Installing Node.js via package manager
```
curl --silent --location https://deb.nodesource.com/setup_0.12 | bash -
apt-get install -y nodejs build-essential
npm install npm -g
npm install bower -g
npm install gulp -g
npm install rimraf -g
npm install gulp-image-resize -g
npm install gulp-imagemin -g
npm install gulp-replace -g
```

#создаем VirtualHost для сайта
```
cd /etc/apache2/sites-available
nano mysite.conf

put VirtualHost text here
then save and exit

cd ../sites-enabled
ln -s ../sites-available/mysite.conf
service apache2 restart
```

#Теперь ставим сайт
- ставим Laravel в папку /var/www/mysite.ru
- меняем владельца и группу с root на www-data 
- настраиваем права для папок
- соединяем репозиторий на гитхабе с папкой сайта
```
cd /var/www
laravel new mysite.ru
chown -R www-data:www-data /var/www/mysite.ru
cd steklo-grup.ru
chmod -R 755 .
chmod -R 777 storage
git init
git add .
git commit -m "Init"
git remote add origin https://github.com/schel4ok/lara.git
git push -u origin master
```

Для обновления laravel и расширений прописанных в composer.json надо, находясь в папке /var/www/steklo-grup.ru запустить команду 
composer update


далее удобней редактировать код прямо на гитхабе, потом загружать изменения на сервер при помощи команды 
*git pull
