# Основы работы Node.js

## Запускаем js файлы
Создаём файл `index.js`:

    const now = new Date().toLocaleString()
    console.log(now)
    console.log(now)

`node index.js` - запускаем скрипт в консоли *(можно без расширения, index)*.

## Встроенные модули Node.js

    // Подключаем модуль работы с файлами
    const fs = require('fs')

    const data = 'Hello World'

    // Создаём файл
    fs.writeFileSync('nodejs.txt', data)

`node index.js` - запускаем скрипт в консоли.

    // Читаем файл
    const data = fs.readFileSync('nodejs.txt', {encoding: 'utf-8'})
    console.log(data)

## Глобальные переменные Node.js

    // Путь до текущей папке
    console.log(__dirname)
    
    // Название текущего файла
    console.log(__filename)
