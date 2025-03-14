# playsdev-hackaton-task2

## Задачи:

- [x] Накатить NGINX, создать репозиторий на GitHub (GitLab) для сохранение всех конфигов nginx, docker и тд. 
- [x] Реализовать обратный прокси на базе NGINX, который будет проксировать запросы на локальную машину, другой порт или другой сервер. 
- [x] Добавить редирект с 80 на 443 порт для всех подключений. 
- [ ] Создать дэфолтную страницу со следующим контентом (прим):
    - [ ] перейти на другую страничку (гиперссылка)
    - [ ] переход на другую траницу, которая обрабатывается этим же nginx (host/secondpage) 
    - [ ] скачать музыку (гиперссылка), при нажатии происходит скачивание музыкального файла (host/music) . 
    - [ ] получить информацию о PHP сервере (гиперссылка) - переход на apache с возвратом инфы о PHP (host/info. php) 
    - [ ] получить респонс с другого сервера (гиперссылка) - сайт который отдается не proxy, а другим сервером (host/secondserver)”

- [x] Создать ещё два сервера в nginx и сделать переход по /redblue так, чтобы при обновлении страницы происходило чередование красной и синей страниц. Для этого необходимо задействовать балансировку и проксирование.

- [ ] Создать переход на /image1 для jpg и /image2 для png. 
Сделать регулярное выражение для картинок: если формат jpg, то картинка будет перевёрнута с помощью nginx.

- [ ] Вывести загрузку CPU на страничку NGINX в реалтайме.

- [ ] Зарегистрироваться на сайте: https://www.noip.com/ (или аналог). Сделать DNS запись типа А, для своего тестового сервера. Получить сертификат безопасности (SSL) с помощь Letsencrypt, webroot и тп. Cайт должен работать только по HTTPS

- [ ] Создать демон процесс, который будет писать раз в 5 секунд логи NGINX в файл 1 (при попытке грохнуть процесс, он должен перезапускаться). Когда файл 1 достигнет размера больше чем 300 кб, он должен очищаться. В файле 2 должен присутствовать лог об удачных очистках файла 1 с датой и временем очистки, а также количеством удаленных записей. В 3 файл складывать логи с 5хх. В 4 файл складывать логи с 4хх. Логи NGNIX можно сохранять любые до каких получится дотянуться. Для парсинга логов использовать sed и awk

## Usage

To generate selfsigned ssl certificate

```
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout reverse-proxy/cert/playsdev.key -out reverse-proxy/cert/playsdev.crt
```

Create a strong Diffie-Hellman group:
```
openssl dhparam -out reverse-proxy/cert/dhparam.pem 2048
```