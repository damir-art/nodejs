# Обработка формы
Устанавливаем пакет https://www.npmjs.com/package/body-parser `npm i body-parser`

## index.js

    // Подключение модуля веб-сервера
    const express = require('express')
    const bodyParser = require('body-parser')

    // Объект сервера (инициализация сервера)
    const app = express()

    // Запускать файлы ejs по-умолчанию
    app.set('view engine', 'ejs')
    // Статические файлы
    app.use(express.static('public'))
    app.use(bodyParser.urlencoded({extended: true}))

    // GET-запрос на сервер и ответ
    // req - отправка, res - ответ
    app.get('/', (req, res) => {
        res.render('index')
    })

    app.post('/', (req, res) => {
        const { city } = req.body
        console.log(city)
        res.render('index')
    })

    // Запуск сервера, на порт 3000
    app.listen(3000, () => {
        console.log('START SERVER')
    })
