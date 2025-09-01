# "VSL" Guide

В этом файле, краткий гайд на то, как мигрироваь с текущей конфигурации лендингов группы **VSL**, к тому коду, что мы ожидаем.


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


## 3. Работа с формой и отправка запроса к PP

В лендингах отправка формы реализована по разному, но давайте попробуем все объединить в один подход:

1. Все запросы в PP - происходят на сервере: для этого создайте `order.php` и укажите его в аттрибут `action`.
2. Уберите все лишние PHP файлы и постарайтесь сделать `order.php` очень простым:

    #### Было:
    ```php
    <?php
    if (empty( $_POST )) die("Bad request");
    $urls = [ "https://cashfactories.com/api/wm/push.json?id=1175-1217ed52ef2d899ddd0f8ee908003a02&offer=1723&flow=19276" ];
    $data = $_POST;
    $data["utm_source"] = $_POST['name'];
    $data["utm_campaign"] = $_POST['phone'];
    $data["ip"] = $_SERVER["HTTP_CF_CONNECTING_IP"] ? $_SERVER["HTTP_CF_CONNECTING_IP"] : ( $_SERVER["HTTP_X_FORWARDED_FOR"] ? $_SERVER["HTTP_X_FORWARDED_FOR"] : $_SERVER["REMOTE_ADDR"] );
    $data["ua"] = $_SERVER["HTTP_USER_AGENT"];
    $data["domain"] = $_SERVER["HTTP_X_FORWARDED_HOST"] ? $_SERVER["HTTP_X_FORWARDED_HOST"] : ( $_SERVER["HTTP_X_HOST"] ? $_SERVER["HTTP_X_HOST"] : ( $_SERVER["HTTP_HOST"] ? $_SERVER["HTTP_HOST"] : $_SERVER["SERVER_NAME"] ) );
    if (isset( $data["phonecc"] )) $data["phone"] = $data["phonecc"].$data["phone"];
    $data = http_build_query( $data );
    foreach ( $urls as $url ) {
    	$curl = curl_init( $url );
    	curl_setopt( $curl, CURLOPT_RETURNTRANSFER, true );
    	curl_setopt( $curl, CURLOPT_TIMEOUT, 65 );
    	curl_setopt( $curl, CURLOPT_POST, 1 );
    	curl_setopt( $curl, CURLOPT_POSTFIELDS, $data );
    	curl_setopt( $curl, CURLOPT_USERAGENT, $_SERVER["HTTP_USER_AGENT"] );
    	curl_setopt( $curl, CURLOPT_SSL_VERIFYHOST, 0 );
    	curl_setopt( $curl, CURLOPT_SSL_VERIFYPEER, 0 );
    	$result = json_decode( curl_exec( $curl ), true );
    	curl_close( $curl );
    	if ( $result ) break;
    }
    if (count( $_GET )) $result = array_merge( $result, $_GET );
    header( "Location: success.php?tax=" . $_POST['tax'] . '&name=' . $_POST['name'] . '&phone=' . $_POST['phone'] . "&" . http_build_query($result) );
    die();
    ?>
    ```

    #### Стало:
    ```php
    <?php
    
    $apiUrl = "https://cashfactories.com/api/wm/push.json?id=1175-1217ed52ef2d899ddd0f8ee908003a02&offer=1723&flow=19276";
    
    if ($_SERVER['REQUEST_METHOD'] === 'POST') {
        $data = [
            'name'        => $_POST['name'],
            'phone'       => !empty($_POST['phonecc']) ? $_POST['phonecc'].$_POST['phone'] : $_POST['phone'],
            'comments'    => $_POST['comments'] ?? '',
            'address'     => $_POST['address'] ?? '',
            'utm_source'  => $_POST['name'] ?? '',
            'utm_campaign'=> $_POST['phone'] ?? '',
            'ip'          => $_SERVER['HTTP_CF_CONNECTING_IP'] ?? $_SERVER['HTTP_X_FORWARDED_FOR'] ?? $_SERVER['REMOTE_ADDR'],
            'ua'          => $_SERVER['HTTP_USER_AGENT'],
            'domain'      => $_SERVER['HTTP_X_FORWARDED_HOST'] ?? $_SERVER['HTTP_X_HOST'] ?? $_SERVER['HTTP_HOST'] ?? $_SERVER['SERVER_NAME'],
        ];
    
        $ch = curl_init($apiUrl);
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($ch, CURLOPT_POSTFIELDS, http_build_query($data));
        curl_setopt($ch, CURLOPT_HTTPHEADER, ['Content-Type: application/x-www-form-urlencoded']);
        curl_setopt($ch, CURLOPT_TIMEOUT, 15);
        curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, 0);
        curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, 0);
        $response = curl_exec($ch);
        curl_close($ch);
    
        $result = json_decode($response, true) ?? [];
    
        $query = http_build_query([
            'tax'   => $_POST['tax'] ?? '',
            'name'  => $_POST['name'] ?? '',
            'phone' => $_POST['phone'] ?? '',
        ] + $result);
    
        header("Location: success.php?$query");
        exit;
    }
    ```

3. Пожалуйста, сделайте **обычный** запрос: никаких классов, дополнительных файлов и тд.
4. Используй **ТОЛЬКО** `curl` вместо каких либо запросов, удалите все другие хендлеры запросов - используйте только `curl`.
5. Уберите все лишние PHP файлы и постарайтесь сделать `order.php` очень простым. — нужно подробнее тут что можно убрать, а что нет, на одном каком-нибудь примере.

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

## 4. Даты

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






2) Все файлы (изображения, видео) — только локально — уточнить, что файлы делать в webp формате (см статью https://yellowweb.top/maksimalnoe-uskorenie-vse-sposoby-sdelat-zagruzku-lendingov-bystree/) сразу же приложить комментом ссылку на конвертер в webp формат
