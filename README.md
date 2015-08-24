сначала надо обновить ОС
```
apt-get update -y && apt-get upgrade -y
```

потом ставим разные полезные утилиты
```
apt-get install mc nano vsftpd -y    
```

далее ставим компоненты веб-сервера
```
apt-get install apache2 php5 libapache2-mod-php5 php5-fpm mysql-server mysql-client php5-mysql  php5-curl  curl phpmyadmin git -y
```

когда phpMyAdmin спросит *Выберите веб-сервер, который будет автоматически настроен для запуска phpMyAdmin.* 
Веб-сервер для автоматической перенастройки:                                    
[ ] apache2     - Выбираем именно apache2!

Для Laravel нужен composer!
нестандартная установка композера (глобально)
```
cd /tmp
curl -sS https://raw.githubusercontent.com/mekras/composer-wrap/master/composer | php
mv composer /usr/bin/composer
composer
```

устанавливаем laravel installer globally
```
composer global require "laravel/installer=~1.1"
```
