сначала надо обновить ОС, но при обновлении командой `apt-get update -y` в конце возникает такая ошибка
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

теперь можно обновлять ОС
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
