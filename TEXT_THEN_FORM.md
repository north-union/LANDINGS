
# "Text Then Form" Guide

В этом файле, краткий гайд на то, как мигрироваь с текущей конфигурации лендингов группы **VSL**, к тому коду, что мы ожидаем.


<img width="1624" height="1011" alt="image" src="https://github.com/user-attachments/assets/c0494881-882e-4b68-9249-72ccf9b621a1" />


> [!IMPORTANT]
> Важно понимать, что я рассматриваю миграцию на одном проекте из общей массы всех лендингов, так что, ваш изначальный код может быть не эквивалентен тому исходному коду, что я сейчас разбираю.


<br />

## 1. Структура папок
### Было:
```
└── 📁26420_offer_archive
    └── 📁css
        ├── application_base-079c7b4e.css
        ├── application_print-83681403.css
        ├── application-e2469c7cf46997a6a8bc882b3a72c4c6aff5e253e1f71c9fe88ef51e329e9ce7.css
        ├── application.css
        ├── orderForm.css
    └── 📁fonts
        ├── Roboto-Bold-08cb8f79715774f9a6285ee7db2919a3-1.woff
        ├── Roboto-Bold-08cb8f79715774f9a6285ee7db2919a3.woff
        ├── Roboto-Bold-f3a02e2578bee50e620e515912278bc9-1.woff2
        ├── Roboto-Bold-f3a02e2578bee50e620e515912278bc9.woff2
        ├── Roboto-BoldItalic-65c7b0c96d644be47ca4a652b2d47972-1.woff
        ├── Roboto-BoldItalic-65c7b0c96d644be47ca4a652b2d47972.woff
        ├── Roboto-BoldItalic-fb87f577cddc4fcce562196d62d86a7c-1.woff2
        ├── Roboto-BoldItalic-fb87f577cddc4fcce562196d62d86a7c.woff2
        ├── Roboto-Italic-ad4e08740474893c8f08df87268544ce-1.woff2
        ├── Roboto-Italic-ad4e08740474893c8f08df87268544ce.woff2
        ├── Roboto-Italic-fd5970128586cba8e7ed994f134ec176-1.woff
        ├── Roboto-Italic-fd5970128586cba8e7ed994f134ec176.woff
        ├── Roboto-Medium-50d01d3e6c994995bcaf829e63d53d1a-1.woff2
        ├── Roboto-Medium-50d01d3e6c994995bcaf829e63d53d1a.woff2
        ├── Roboto-Medium-9a3bf7acae14d9b5ed5a88458106b58b-1.woff
        ├── Roboto-Medium-9a3bf7acae14d9b5ed5a88458106b58b.woff
        ├── Roboto-Regular-94dac78eee406a8c8f0406b69b85ac2b-1.woff
        ├── Roboto-Regular-94dac78eee406a8c8f0406b69b85ac2b.woff
        ├── Roboto-Regular-9feb0110b6dff9ee2b9ebd17f7a1aee6-1.woff2
        ├── Roboto-Regular-9feb0110b6dff9ee2b9ebd17f7a1aee6.woff2
    └── 📁images
        └── 📁com-ge
            ├── m1.jpg
            ├── m10.jpg
            ├── m11.jpg
            ├── m12.jpg
            ├── m13.jpg
            ├── m14.jpg
            ├── m15.jpg
            ├── m16.jpg
            ├── m17.jpg
            ├── m18.jpg
            ├── m19.jpg
            ├── m2.jpg
            ├── m20.jpg
            ├── m21.jpg
            ├── m3.jpg
            ├── m4.jpg
            ├── m5.jpg
            ├── m6.jpg
            ├── m7.jpg
            ├── m8.jpg
            ├── m9.jpg
            ├── w1.jpg
            ├── w10.jpg
            ├── w11.jpg
            ├── w12.jpg
            ├── w13.jpg
            ├── w14.jpg
            ├── w15.jpg
            ├── w16.jpg
            ├── w17.jpg
            ├── w18.jpg
            ├── w19.jpg
            ├── w2.jpg
            ├── w20.jpg
            ├── w21.jpg
            ├── w3.jpg
            ├── w4.jpg
            ├── w5.jpg
            ├── w6.jpg
            ├── w7.jpg
            ├── w8.jpg
            ├── w9.jpg
        ├── .DS_Store
        ├── 1-academicianul-leon-danaila-portret.jpg
        ├── ava_w13.jpg
        ├── back-main3.jpg
        ├── blood-and-calcium-2.jpg
        ├── default-ava.jpg
        ├── doc_default.jpg
        ├── domino11.jpg
        ├── favicon.ico
        ├── formbg-nobord.jpg
        ├── header.jpg
        ├── headerm.jpg
        ├── m_7.jpg
        ├── main-grandma.png
        ├── oper-hearth4.jpg
        ├── oper-info3.jpg
        ├── otz-rev1.jpg
        ├── otz-rev13.jpg
        ├── otz-rev2.jpg
        ├── otz-rev5.jpg
        ├── otz-rev8.jpg
        ├── pattern-bg-footer.png
        ├── product.png
        ├── seleb_default.jpg
        ├── sosud-4.jpg
    ├── _preview.png
    ├── .DS_Store
    ├── back.js
    ├── dtime.js
    ├── index.php
    ├── order.php
    └── success.php
```

### Стало:
```
└── 📁26420_offer_archive [UPGRADE]
    └── 📁assets
        └── 📁fonts
            ├── Roboto-Bold-08cb8f79715774f9a6285ee7db2919a3-1.woff
            ├── Roboto-Bold-08cb8f79715774f9a6285ee7db2919a3.woff
            ├── Roboto-Bold-f3a02e2578bee50e620e515912278bc9-1.woff2
            ├── Roboto-Bold-f3a02e2578bee50e620e515912278bc9.woff2
            ├── Roboto-BoldItalic-65c7b0c96d644be47ca4a652b2d47972-1.woff
            ├── Roboto-BoldItalic-65c7b0c96d644be47ca4a652b2d47972.woff
            ├── Roboto-BoldItalic-fb87f577cddc4fcce562196d62d86a7c-1.woff2
            ├── Roboto-BoldItalic-fb87f577cddc4fcce562196d62d86a7c.woff2
            ├── Roboto-Italic-ad4e08740474893c8f08df87268544ce-1.woff2
            ├── Roboto-Italic-ad4e08740474893c8f08df87268544ce.woff2
            ├── Roboto-Italic-fd5970128586cba8e7ed994f134ec176-1.woff
            ├── Roboto-Italic-fd5970128586cba8e7ed994f134ec176.woff
            ├── Roboto-Medium-50d01d3e6c994995bcaf829e63d53d1a-1.woff2
            ├── Roboto-Medium-50d01d3e6c994995bcaf829e63d53d1a.woff2
            ├── Roboto-Medium-9a3bf7acae14d9b5ed5a88458106b58b-1.woff
            ├── Roboto-Medium-9a3bf7acae14d9b5ed5a88458106b58b.woff
            ├── Roboto-Regular-94dac78eee406a8c8f0406b69b85ac2b-1.woff
            ├── Roboto-Regular-94dac78eee406a8c8f0406b69b85ac2b.woff
            ├── Roboto-Regular-9feb0110b6dff9ee2b9ebd17f7a1aee6-1.woff2
            ├── Roboto-Regular-9feb0110b6dff9ee2b9ebd17f7a1aee6.woff2
        └── 📁images
            └── 📁com-ge
                ├── m1.jpg
                ├── m10.jpg
                ├── m11.jpg
                ├── m12.jpg
                ├── m13.jpg
                ├── m14.jpg
                ├── m15.jpg
                ├── m16.jpg
                ├── m17.jpg
                ├── m18.jpg
                ├── m19.jpg
                ├── m2.jpg
                ├── m20.jpg
                ├── m21.jpg
                ├── m3.jpg
                ├── m4.jpg
                ├── m5.jpg
                ├── m6.jpg
                ├── m7.jpg
                ├── m8.jpg
                ├── m9.jpg
                ├── w1.jpg
                ├── w10.jpg
                ├── w11.jpg
                ├── w12.jpg
                ├── w13.jpg
                ├── w14.jpg
                ├── w15.jpg
                ├── w16.jpg
                ├── w17.jpg
                ├── w18.jpg
                ├── w19.jpg
                ├── w2.jpg
                ├── w20.jpg
                ├── w21.jpg
                ├── w3.jpg
                ├── w4.jpg
                ├── w5.jpg
                ├── w6.jpg
                ├── w7.jpg
                ├── w8.jpg
                ├── w9.jpg
            ├── .DS_Store
            ├── 1-academicianul-leon-danaila-portret.jpg
            ├── ava_w13.jpg
            ├── back-main3.jpg
            ├── blood-and-calcium-2.jpg
            ├── default-ava.jpg
            ├── doc_default.jpg
            ├── domino11.jpg
            ├── favicon.ico
            ├── formbg-nobord.jpg
            ├── header.jpg
            ├── headerm.jpg
            ├── m_7.jpg
            ├── main-grandma.png
            ├── oper-hearth4.jpg
            ├── oper-info3.jpg
            ├── otz-rev1.jpg
            ├── otz-rev13.jpg
            ├── otz-rev2.jpg
            ├── otz-rev5.jpg
            ├── otz-rev8.jpg
            ├── pattern-bg-footer.png
            ├── product.png
            ├── seleb_default.jpg
            ├── sosud-4.jpg
    ├── _preview.png
    ├── .DS_Store
    ├── history-back.js
    ├── index.css
    ├── index.js
    ├── index.php
    ├── order.php
    └── success.php
```

<br />

1. В проекте давайте оставим только следующе обязательные файлы: `index.php`, `index.css`, `index.js`, `history-back.js` (бывший `back.js`).
2. Если у вас есть любые другие js файлы, либо css файлы — совместите их в один файл.
3. Уберем все файлы подключения стороних, локальных библиотек, которые возможно подключить прямо в html — это намного лучше.

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

5. Учитывая, что в каждом лендинге своя работа с видео и его ивентами, ниже пример рабочего хендлера для видео, которое отвечает за скрытие, отображение видео и работу таймера, **важно**: если у вас все равно работает хендлинг видео, то в любом случае перепишите код на данный подход:
```js
const sectionForm = document.querySelector(".section-form");

function createTimer(element) {
    const startTime = Date.now();
    const endTime = startTime + 10 * 60 * 1000;
    function updateTimer() {
        const remainingTime = endTime - Date.now();
        const minutes = Math.floor((remainingTime / (1000 * 60)) % 60);
        const seconds = Math.floor((remainingTime / 1000) % 60);
        const formattedTime = `${minutes
            .toString()
            .padStart(2, "0")}:${seconds.toString().padStart(2, "0")}`;
        element.textContent = formattedTime;
        if (remainingTime <= 0) {
            clearInterval(timerInterval);
            element.textContent = "00:00";
        }
    }
    const timerInterval = setInterval(updateTimer, 100);
    updateTimer();
}
const timerElements = document.querySelectorAll(".my-timer-now");


let video = document.querySelector("video");

if (video) {
    console.log("video найден при загрузке:", video);
    setupVideoEvents(video);
} else {
    const observer = new MutationObserver(function(mutationsList) {
        mutationsList.forEach(function(mutation) {
            if (mutation.type === "childList") {
                mutation.addedNodes.forEach(function(node) {
                    if (node.tagName === "VIDEO") {
                        console.log("video было добавлено:", node);
                        video = node;
                        setupVideoEvents(video);
                    }
                });
            }
        });
    });
    observer.observe(document.body, { childList: true, subtree: true });
}

function setEndVideo() {
    sectionForm.classList.remove("none");
    timerElements.forEach((element) => {
        createTimer(element);
    });
    const orderElement = document.getElementById("order");
    if (orderElement) {
        orderElement.scrollIntoView({ behavior: "smooth" });
    }
}

function setupVideoEvents(video) {
    video.addEventListener("ended", function() {
        setEndVideo();
    });
}
```

6. **Важно**, в консоли, у вас возможно будет ошибка `Uncaught ReferenceError: wrapper is not defined` - не обращайте внимание, это ошибка подгружаемого скрипта, но если вы заметили что у вас в коде, есть переменная с названием `wrapper`, пожалуйста, переименуйте ее **и дайте мне знать, обязательно.** Такая необходимость связана с тем, что некоторые лендинги обращаются не к своим локальным переменным, а к переменным подгружаемый из скрипта — это безусловно плохая практика, но работаем с тем, что есть.
<img width="1624" height="1011" alt="image" src="https://github.com/user-attachments/assets/c05de423-e148-4a18-aa75-1f334412d0c5" />


## 4. Работа с формой и отправка запроса к PP

В лендингах отправка формы реализована по разному, но давайте попробуем все объединить в один подход:

1. Все запросы в PP - происходят на сервере: для этого создайте `order.php` и укажите его в аттрибут `action`.
2. Уберите все лишние PHP файлы и постарайтесь сделать `order.php` очень простым.
3. Пожалуйста, сделайте **обычный** запрос: никаких классов, дополнительных файлов и тд.
4. Используй **ТОЛЬКО** `curl` вместо каких либо запросов, удалите все другие хендлеры запросов - используйте только `curl`.

### Было:
```php
<?php

$apiKey = '###';
$offer_id = 14612;
$stream_hid = 'PQnSKqMg';
$country = 'EG';
$timezone_int = '4';
$apiUrl = '###';
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
<?php

$apiUrl = '###';
$apiKey = '###';
$offer_id = 14612;
$stream_hid = 'PQnSKqMg';
$country = 'EG';
$timezone_int = '4';

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $data = [
        'key'         => $apiKey,
        'id'          => microtime(true),
        'offer_id'    => $offer_id,
        'stream_hid'  => $stream_hid,
        'name'        => $_POST['name'],
        'phone'       => $_POST['phone'],
        'comments'    => $_POST['comments'],
        'address'     => $_POST['address'],
        'country'     => $country,
        'tz'          => $timezone_int,
        'web_id'      => '',
        'ip_address'  => $_SERVER['HTTP_CF_CONNECTING_IP'] ?? $_SERVER['REMOTE_ADDR'],
        'user_agent'  => $_SERVER['HTTP_USER_AGENT'],
        'sub1'        => $_POST['sub1'],
        'sub2'        => $_POST['sub2'],
        'sub3'        => $_POST['sub3'],
        'sub4'        => $_POST['sub4'],
        'sub5'        => $_POST['sub5'],
    ];

    $ch = curl_init($apiUrl);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_POSTFIELDS, http_build_query($data));
    curl_setopt($ch, CURLOPT_HTTPHEADER, ['Content-Type: application/x-www-form-urlencoded']);
    $response = curl_exec($ch);
    curl_close($ch);

    $result = json_decode($response);
    header('Location: success.php?id_zayavki=' . $result->id);
    exit;
}
```


> [!CAUTION]
> Помните, что данный гайд — обслуживает персональный кейс. Отвественность за работоспособность лендинга в любом случае лежит на том, кто заливает код в прод. Поэтому обязательно, проверьте запросы подняв локальный эндпоинт. Обязательно, тк запросы к PP не нужно заливать на прод, заранее не протестив.

<br />

## 5. Даты

Оставьте работу с датами как есть — если она уже работает, не трогайте ее.

<br />
<br />

## Обязательные требования, внезависимости от типа лендинга:

> [!CAUTION]
> Ваш лендинг может полностью соответствовать рекомендациям выше, но чеклист ниже - обязателен к ознакомлению, убедитесь что все соблюдено.


1. Никаких ключей в клиентской части (HTML, JS) — только PHP.
2. Никаких странных файлов в директории: `.DS_Store`, `log.txt` и прочие файлы, оставьте только служебные файлы, которые были упомянуты в первом пункте.
3. [Никаких `eval` и подобных функций](https://docs.keitaro.io/ru/landing-pages-and-offers/landing-page-local.html?h=eval).
4. [При загрузке дополнительных скриптов в include() и require() используется полный путь до файла (например, с dirname(__FILE__))](https://docs.keitaro.io/ru/landing-pages-and-offers/landing-page-local.html?h=require).
5. [Удалите теги `base` в вашем HTML коде](https://docs.keitaro.io/ru/landing-pages-and-offers/landing-page-local.html?h=require#%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D0%BA-%D0%BB%D0%B5%D0%BD%D0%B4%D0%B8%D0%BD%D0%B3%D0%B0%D0%BC).
6. Удалите ВСЕ комментарии, они не нужны.
7. Уберите все `<script>` в вашем HTML — мигрируйте их в JS файл, также уберите все `<style>` теги.




<br />
<br />

## Feedback
1. Если вы понимаете, что пункт инструкции **не работает** - обязательно составьте pull request прямо в этом репозитории.
2. Если вы понимаете, что пункт инструкции **не оптимален** - обязательно составьте pull request прямо в этом репозитории.
