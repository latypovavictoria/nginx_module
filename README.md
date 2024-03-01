# nginx_module
Test task for nginx module

#### How to start?

Для начала необходимо склонировать репозиторий.

Обновить менеджер пакетов Ubuntu.

```
sudo apt-get update
```
Установить библиотеки разработки.
```
sudo apt-get install build-essential libpcre3 libpcre3-dev zlib1g zlib1g-dev libssl-dev libgd-dev libxml2 libxml2-dev uuid-dev
```

После этого перейти в папку и последовательно выполнить команды:
```
./configure
```
Скомпилировать исходный код NGINX с помощью этой команды:
```
make
```
Установить скомпилированный исходный код:
```
sudo make install
```
Перейти в дирректорию ```objs``` и сделать start nginx:
```
cd objs
```
```
sudo ./nginx
```
Чтобы настроить логирование nginx, необходимо перейти в дирректорию ```/usr/local/nginx/conf``` и вписать следующие строки в конфигурационный файл ```nginx.conf```:
```
error_log  logs/error.log;
error_log  logs/error.log  notice;
error_log  logs/error.log  info;
error_log  logs/error.log debug;
```
Далее перейти в дирректорию ```objs``` и перезагрузить nginx:
```
sudo ./nginx -s reload
```
После отправки запросов, логи можно посмотреть по пути ```/usr/local/nginx/logs/error.log```
