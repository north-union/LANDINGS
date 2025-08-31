# "Video First" Guide

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
2. Если у вас есть любые другие js файлы, либо css файлы — совместите их в один файл.
3. Уберем все файлы подключения стороних библиотек, которые возможно подключить прямо в html — это намного лучше.

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


## 2. Изменение плеера

С недавних пор, у нас появился `videomaxhost.cloud` плеер, поэтому нам необходимо мигрировать с текущего VTube на наш плеер, если вы пропустили момент ознакомления, [то рекоммендую посмотреть это видео](https://github.com/north-union/README).

### Было:

<img width="1624" height="1011" alt="image" src="https://github.com/user-attachments/assets/9081820f-365e-4557-a936-091a22152bff" />

### Стало:

<img width="1624" height="1011" alt="image" src="https://github.com/user-attachments/assets/ced384fa-5ac8-496e-9641-acd5e4980cc9" />


1. Удалить текущую интеграцию и изображение-превью:
```html
<div id="vid_687a468bea27916e7c73e594" style="position: relative; width: 100%; padding: 56.25% 0 0;"> <img id="thumb_687a468bea27916e7c73e594" src="https://images.converteai.net/582790c2-e21b-4886-af13-d25e7060df14/players/687a468bea27916e7c73e594/thumbnail.jpg" style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; object-fit: cover; display: block;" alt="thumbnail">
    <div id="backdrop_687a468bea27916e7c73e594" style=" -webkit-backdrop-filter: blur(5px); backdrop-filter: blur(5px); position: absolute; top: 0; height: 100%; width: 100%; ">
    </div>
</div>

<script type="text/javascript" id="scr_687a468bea27916e7c73e594">
    var s = document.createElement("script");
    s.src = "https://scripts.converteai.net/582790c2-e21b-4886-af13-d25e7060df14/players/687a468bea27916e7c73e594/player.js", s.async = !0, document.head.appendChild(s);
</script>

<img src="img/news-logos.webp" class="img_adv">
```
2. Подключите скрипт для подключения к `videomaxhost.cloud`:
```html
 <script type="text/javascript" src="https://player.videomaxhost.cloud/embed.js"></script>
```
3. Подключите виджет:
```html
<div class="embedpvideo" data-videoid="33559eb3-23c9-49c8-80fb-3e2fba32f8cd"></div>
```
4. Если вы видите, что видео не подгрузилось или не отображается — значит ваш текущий JS файл содержит ту логику, которая была совместима ТОЛЬКО с VTube. Учитывая, что лендингов слишком много, а реализаций еще больше — то вот, минимальный flow для работы видео:
```js
let video = document.querySelector("video");

if (video) {
    console.log("video найден при загрузке:", video);
    setupVideoEvents(video);
} else {
    const observer = new MutationObserver((mutationsList) => {
        mutationsList.forEach((mutation) => {
            if (mutation.type === "childList") {
                mutation.addedNodes.forEach((node) => {
                    if (node.tagName === "VIDEO") {
                        video = node;
                        setupVideoEvents(video);
                        observer.disconnect(); // Останавливаем наблюдатель
                    }
                });
            }
        });
    });
    observer.observe(document.body, { childList: true, subtree: true });
}
```

## 4. Работа с формой и отправка запроса к PP

В лендингах отправка формы реализована по разному, но давайте попробуем все объединить в один подход:

1. Все запросы в PP - происходят на сервере: для этого создайте `order.php` и укажите его в аттрибут `action`.
2. Уберите все лишние PHP файлы и постарайтесь сделать `order.php` очень простым.
3. Пожалуйста, сделайте **обычный** запрос: никаких классов, дополнительных файлов и тд.
4. Используй **ТОЛЬКО** `curl` вместо каких либо запросов, удалите все другие хендлеры запросов - используйте только `curl`.

### Было:
```php
<?php

$apiKey = 'AC1XNexHsXaInMoGM8ZTsteba8XpZGZ10';
$offer_id = 14612;
$stream_hid = 'PQnSKqMg';
$country = 'EG';
$timezone_int = '4';
$apiUrl = 'http://api.cpa.tl/api/lead/send';
$name = $_POST['name'];
$phone = $_POST['phone'];
if ($_SERVER['REQUEST_METHOD'] == 'POST') {
    $data_post = $_POST;

    $data = array(
            'key' => $apiKey,
            'id' => microtime(true), // тут лучше вставить значение, по которому вы сможете идентифицировать свой лид; можно оставить microtime если у вас нет своей crm
            'offer_id' => $offer_id,
            'stream_hid' => $stream_hid,
            'name' => $name,
            'phone' => $phone,
            'comments' => $data_post['comments'],
            'country' => $country, // формат ISO 3166-1 Alpha-2 - https://ru.wikipedia.org/wiki/ISO_3166-1
            'address' => $data_post['address'],
            'tz' => $timezone_int, // очень желательно получать его с ленда, но если никак лучше оставить пустым или 3 (таймзона мск)
            'web_id' => '',
            'ip_address' => isset($_SERVER["HTTP_CF_CONNECTING_IP"]) ? $_SERVER["HTTP_CF_CONNECTING_IP"] : $_SERVER['REMOTE_ADDR'],
            'user_agent' => $_SERVER['HTTP_USER_AGENT'],
            'sub1' => $_POST['sub1'],
            'sub2' => $_POST['sub2'],
            'sub3' => $_POST['sub3'],
            'sub4' => $_POST['sub4'],
            'sub5' => $_POST['sub5'],
    );

    $options = array(
            'http' => array(
                'header' => "Content-type: application/x-www-form-urlencoded\r\n",
                'method' => 'POST',
                'content' => http_build_query($data),
                'ignore_errors' => true,
            )
    );

    $context = stream_context_create($options);
    $result = file_get_contents($apiUrl, false, $context);

    $obj = json_decode($result);

    if (null === $obj) {
            // Ошибка в полученном ответе
            print("Invalid JSON");
        } else if (!empty($obj->errmsg)) {
            // Ошибка в отправленном запросе
            print("Ошибка: " . $оbj->errmsg);
        } else {
            header ('Location: success.php?tax=' . $_POST['tax'] . '&name=' . $data_post['name'] . '&phone=' . $data_post['phone'] . '&id_zayavki=' . $obj->id);
    }

}
```


### Стало:
```php
function sendLead(array $data, string $apiUrl): array {
    $ch = curl_init($apiUrl);
    curl_setopt_array($ch, [
        CURLOPT_POST            => true,
        CURLOPT_POSTFIELDS      => http_build_query($data),
        CURLOPT_RETURNTRANSFER  => true,
        CURLOPT_FOLLOWLOCATION  => true,
        CURLOPT_CONNECTTIMEOUT  => 5,   // таймаут соединения
        CURLOPT_TIMEOUT         => 15,  // общий таймаут
        CURLOPT_HTTPHEADER      => ['Content-Type: application/x-www-form-urlencoded'],
        CURLOPT_SSL_VERIFYPEER  => true,
        CURLOPT_SSL_VERIFYHOST  => 2,
    ]);

    $body = curl_exec($ch);
    $errno = curl_errno($ch);
    $error = curl_error($ch);
    $status = curl_getinfo($ch, CURLINFO_RESPONSE_CODE);
    curl_close($ch);

    if ($errno) {
        throw new RuntimeException("cURL error: $error", $errno);
    }
    if ($status < 200 || $status >= 300) {
        throw new RuntimeException("HTTP $status: $body");
    }

    $json = json_decode($body, true);
    if (json_last_error() !== JSON_ERROR_NONE) {
        throw new RuntimeException("Invalid JSON: $body");
    }
    return $json;
}
```


## 5. Даты

// Дописать это
