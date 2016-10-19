#Edu konspekt

## Forms

## Cookies
* To install: 
```
$ npm install --save cookie-parser
```
* to enable:
```app.use(require('cookie-parser')(credentials.cookieSecret)) ```
* to set cookie
``` res.cookie('monster', 'mom mom'); ```
* to get cookie value
```javascript
var monster = res.cookies.monster;
```
* to delete
```javascript
res.clearCookie('monster');
```
* this optons can be installed by cookie initialization:
 - domain
 - path
 - maxAge
 - secure - https only
 - httpOnly - cookie can be changed only by server.
 - signed ```res.cookies```->```res.signedCookies```   
 
## Session 
* Package name: ```express-session```
* Enable 
```javascript
app.use(require('express-session')({
    resave: false,
    saveUninitialized: false,
    secret: credentials.cookieSecret
}))
```
Get config object with options:
 - **resave** - заставляет сеанс заново сохраняться в хранилище даже если он не был изменен.
 - **saveUninitialized** - сохраняет новын сеансы в хранилище
 - **secret** - ключ для идентификации куки-файла. Может быть ключом что и для cookie-parser
 - **key** - имя куки файла для хранения идентификатора сеанса. По умолчанию ```connect.sid```
 - **store** - экземпляр сеансового хранилища
 - **cookie** - настройки для куки-сеанса. path, domain ...
* Использование сеансов
```req.session.userName = "Anonymus"```

## Tips

* to run mocha test shell it:
```bash
$ mocha -u tdd -R spec public/qa/test-unit.js
```