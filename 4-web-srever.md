# Создаём веб-сервер
Создаём веб-сервер Express

В `index.js` записываем:

    // Подключение модуля веб-сервера
    const express = require('express')

    // Объект сервера (инициализация сервера)
    const app = express()

    // Запуск сервера, на порт 3000
    app.listen(3000, () => {
        console.log('START SERVER')
    })

В консоли пишем `node index`, сервер запустился. Выйти из сервера `Ctrl + C` в консоли.

Если написать `nodemon index`, то тоже запустится сервер, но при этом при редактировании файла не нужно будет отключать и заного включать сервер чтобы посмотреть изменения *(nodemon должен быть установлен глобально)*. Выйти из nodemon `Ctrl + C` в консоли.

Открываем браузер и пишем: `localhost:3000`, откроет страницу с ошибкой `Cannot GET /`, чтобы всё было нормально, нужно написать, под инициализацией сервера:

    // GET-запрос на сервер и ответ
    app.get('/', (req, res) => {
        res.end('Hello from Node.js')
    })

## scripts
Для удобства работы с веб-сервером, в файле package.json изменим объект `scripts`:

    "scripts": {
        "start": "nodemon custom.js",
        "prod": "node custom.js",
    },

Для запуска скриптов, пишем в консоли `npm run start`, `npm run prod` и т.д.
