## Отчёт к лабораторной работе №1  "HTTP HTTPS и их параметры"

### Цель работы
Познакомиться с протоколом HTTP и протоколом HTTPS, а так же особенностями установления соединения между источником и получателем.

### Get запрос
```git
$ curl -I https://lolesports.com
```
Получил код:
```git
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 67584
Connection: keep-alive
Last-Modified: Thu, 09 Nov 2023 18:01:23 GMT
x-amz-server-side-encryption: AES256
Accept-Ranges: bytes
Server: AmazonS3
Date: Tue, 14 Nov 2023 11:06:00 GMT
Cache-Control: no-cache, no-store, must-revalidate
ETag: "7ea634b108589ca5c47aeb315ca4e7a2"
Vary: Accept-Encoding
X-Cache: RefreshHit from cloudfront
Via: 1.1 6b590e690e32695caa633ab770319d74.cloudfront.net (CloudFront)
X-Amz-Cf-Pop: ARN56-P1
X-Amz-Cf-Id: iZs49N8MDIeUbE4xfaMrpb_7KlZCMnTmI-8sAvqQjl9vNY7ohbGeKQ==
```
Описание к коду:
```git
HTTP/1.1 200 OK - код состояния HTTP (200 означает успешный запрос), а также сообщение OK, указывающее, что запрос был выполнен успешно.

Content-Type: text/html - тип содержимого.

Content-Length: 67584 - - это число, обозначающее точную длину байта тела HTTP.

Connection: keep-alive - информация о соединении .В данном случае keep-alive означает что соединение будет удерживаться открытым для последующих запросов.

Last-Modified: Thu, 09 Nov 2023 18:01:23 GMT - дату и время, в которую  запрашиваемый ресурс был изменён.

x-amz-server-side-encryption: AES256 - является заголовком, связанным с сервисом Amazon S3 (Simple Storage Service). Этот заголовок указывает на то, что серверное шифрование данных активировано для объекта, хранящегося в Amazon S3. 

Accept-Ranges: bytes - это маркер, который использует сервер, чтобы уведомить клиента о поддержке "запросов по кускам". Его значение указывает единицу измерения, которая может быть использована для определения диапазона чтения. 

Server: AmazonS3 - информация о сервере

Date: Tue, 14 Nov 2023 11:06:00 GMT - текущая дата и время

Cache-Control: no-cache, no-store, must-revalidate -  – это HTTP-заголовок, который определяет поведение браузера при кэшировании.

ETag: "7ea634b108589ca5c47aeb315ca4e7a2" - это непрозрачный идентификатор, назначенный веб-сервером определенной версии ресурса, найденного по URL-адресу. 

Vary: Accept-Encoding - Vary определяет разделенный запятыми список HTTP-заголовков, которые должны учитываться кэшами вместе с URL-адресом при принятии решения о том, является ли запрос попаданием в кэш или пропущенным.

X-Cache: RefreshHit from cloudfront - заголовок HTTP, который указывает на наличие кэширования на сервере или в прокси-сервере между клиентом и сервером. 

Via: 1.1 6b590e690e32695caa633ab770319d74.cloudfront.net (CloudFront) - - это заголовок HTTP, который указывает на промежуточные прокси-серверы, через которые прошел запрос, начиная от клиента до сервера.

X-Amz-Cf-Pop: ARN56-P1 - это заголовок, который используется в HTTP запросах к сервисам Amazon Web Services (AWS) сетевой доставки контента (Content Delivery Network - CDN) CloudFront. Конкретно этот заголовок обозначает код точки присутствия (POP - Point of Presence) CloudFront, через которую обрабатывается запрос. 

X-Amz-Cf-Id: iZs49N8MDIeUbE4xfaMrpb_7KlZCMnTmI-8sAvqQjl9vNY7ohbGeKQ== - является другим заголовком, который связан с сервисом Amazon Web Services (AWS) CloudFront. Он представляет уникальный идентификатор запроса (Request ID) для конкретной операции, обрабатываемой CloudFront.
```
Вывод: я научился делать get-запросы и понимать полученную информацию.