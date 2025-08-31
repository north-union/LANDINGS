# Video First Guide

В этом файле, краткий гайд на то, как мигрироваь с текущей конфигурации лендингов группы **Video First**, к тому коду, что мы ожидаем.


<img width="1624" height="1011" alt="image" src="https://github.com/user-attachments/assets/8a906627-6ebd-42a3-b8f5-e79ffc6acd52" />


> [!IMPORTANT]
> Важно понимать, что я рассматриваю миграцию на одном проекте из общей массы всех лендингов, так что, ваш изначальный код может быть не эквивалентен тому исходному коду, что я сейчас разбираю.


<br />

## 1. Структура папок
### Было:
```
└── 📁3072_landing_archive
    └── 📁css
        ├── bootstrap.css
        ├── custom.css
        ├── fbcomments.css
        ├── page.css
        ├── vsl.css
    └── 📁img
        └── 📁coments
            ├── 001.jpg
            ├── 002.jpg
            ├── 002.png
            ├── 01.jpg
            ├── 02.jpg
            ├── 03.jpg
            ├── h2.jpg
            ├── user1-1.webp
            ├── user1-2.webp
            ├── user3.webp
        ├── likes.webp
        ├── menu-toggle.webp
        ├── news-logos.webp
        ├── product.png
    └── 📁js
        ├── main.js
    ├── _preview.png
    ├── .DS_Store
    ├── back.js
    └── index.php
```

### Стало:
```
└── 📁3072_landing_archive UPGRADED
    └── 📁assets
        └── 📁img
            └── 📁comments
                ├── 001.jpg
                ├── 002.jpg
                ├── 002.png
                ├── 01.jpg
                ├── 02.jpg
                ├── 03.jpg
                ├── h2.jpg
                ├── user1-1.webp
                ├── user1-2.webp
                ├── user3.webp
            ├── likes.webp
            ├── menu-toggle.webp
            ├── news-logos.webp
            ├── product.png
    ├── _preview.png
    ├── history-back.js
    ├── index.css
    ├── index.js
    └── index.php
```

<br />

1. В проекте давайте оставим только следующе обязательные файлы: `index.php`, `index.css`, `index.js`, `history-back.js` (бывший `back.js`).
2. Уберем все файлы подключения стороних библиотек, которые возможно подключить прямо в html — это намного лучше.

    #### Было: 
    ```html
    <head>
        <meta charset="UTF-8">
        <meta name="referrer" content="no-referrer">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
        <title>
            Doctor Begs: Swap Your Metformin For This "Valacore Blood Support" That Stabilizes Glucose in 72h
        </title>
        <link rel="stylesheet" type="text/css" href="css/page.css">

    
        <link rel="stylesheet" type="text/css" href="css/bootstrap.css"> <!--ТУТ-->


        <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/bootstrap-icons/1.11.3/font/bootstrap-icons.min.css" integrity="sha512-dPXYcDub/aeb08c63jRq/k6GaKccl256JQy/AnOq7CAnEZ9FzSL9wSbcZkMp4R26vBsMLFYH4kQ67/bbV8XaCQ==" crossorigin="anonymous" referrerpolicy="no-referrer" />
        <link rel="stylesheet" type="text/css" href="css/custom.css">
        <link rel="stylesheet" type="text/css" href="css/fbcomments.css">
        <link rel="stylesheet" type="text/css" href="css/vsl.css">
        <script src="js/main.js" defer=""></script>
    </head>
    ```

    #### Стало: 
    ```html
    <head>
        <meta charset="UTF-8">
        <meta name="referrer" content="no-referrer">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
        <title>
            Doctor Begs: Swap Your Metformin For This "Valacore Blood Support" That Stabilizes Glucose in 72h
        </title>
        <link rel="stylesheet" type="text/css" href="css/page.css">

    
        <link
          href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
          rel="stylesheet"
          integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH"
          crossorigin="anonymous"
        /> <!--ТУТ-->

    
        <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/bootstrap-icons/1.11.3/font/bootstrap-icons.min.css" integrity="sha512-dPXYcDub/aeb08c63jRq/k6GaKccl256JQy/AnOq7CAnEZ9FzSL9wSbcZkMp4R26vBsMLFYH4kQ67/bbV8XaCQ==" crossorigin="anonymous" referrerpolicy="no-referrer" />
        <link rel="stylesheet" type="text/css" href="index.css">
        <script src="index.js" defer=""></script>
    </head>
    ```

