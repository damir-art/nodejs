# Создаём веб-страницу
Создаём в корне проекта папки и файлы:

    public/
        css/
            styles.css
    views/
        index.ejs
    index.js

Устанвливаем пакет https://www.npmjs.com/package/ejs `npm i ejs` специальный формат файлов для шаблонизации HTML-файлов.

## index.js

    // Подключение модуля веб-сервера
    const express = require('express')

    // Объект сервера (инициализация сервера)
    const app = express()

    // Запускать файлы ejs по-умолчанию
    app.set('view engine', 'ejs')

    // Статические файлы
    app.use(express.static('public'))

    // GET-запрос на сервер и ответ
    app.get('/', (req, res) => {
        res.render('index')
    })

    // Запуск сервера, на порт 3000
    app.listen(3000, () => {
        console.log('START SERVER')
    })
    
## index.ejs
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">
        <title>Node JS APP</title>
        <link rel="stylesheet" href="/css/styles.css">
    </head>
    <body>
        <div class="app">
            <div class="app__header">
                <h1>Title</h1>
                <p class="error">Some error</p>
            </div> <!-- .app__header -->

            <form action="" class="app__content">
                <div class="input">
                    <label for="city">Город</label>
                    <input type="text" id="city" placeholder="Название города" />
                </div>
                <button type="submit" class="btn">Показать погоду</button>
            </form>
        </div> <!-- .app -->
    </body>
    </html>
