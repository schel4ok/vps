сначала надо обновить ОС
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
apt-get update -y 
apt-get upgrade -y
```

потом ставим разные полезные утилиты
```
apt-get install mc nano vsftpd -y    
```

далее ставим компоненты веб-сервера (кроме nginx, т.к. я с ним пока не разобрался)
```
apt-get install apache2 php5 libapache2-mod-php5 php5-fpm mysql-server mysql-client php5-mysql  php5-curl  curl phpmyadmin git -y
```
когда phpMyAdmin спросит *Выберите веб-сервер, который будет автоматически настроен для запуска phpMyAdmin.*  
Веб-сервер для автоматической перенастройки:  
[] apache2     - Выбираем именно apache2!  
потом на вопрос **configure database for phpmyadmin with dbconfig-common** отвечаем нет  

Для Laravel нужен composer!  
установка композера глобально (это composer-wrap вместо стандартного композера, который позволяет устанавливать пакеты типа laravel глобально для всех пользователей, а не только для root)
```
git clone https://github.com/mekras/composer-wrap
mv composer-wrap/composer /usr/local/bin/composer
rm -r composer-wrap
```

устанавливаем laravel installer globally
```
composer global require "laravel/installer=~1.1"
```

Installing Node.js via package manager
```
curl --silent --location https://deb.nodesource.com/setup_0.12 | bash -
apt-get install -y nodejs build-essential npm
npm install npm -g
npm install bower gulp laravel-elixir gulp-imagemin gulp-image-resize -g  
```
