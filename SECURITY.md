## Обязательные требования, внезависимости от типа лендинга:

> [!CAUTION]
> Ваш лендинг может полностью соответствовать рекомендациям выше, но чеклист ниже - обязателен к ознакомлению, убедитесь что все соблюдено.


1. Никаких ключей в клиентской части (HTML, JS) — только PHP.
2. Никаких странных файлов в директории: `.DS_Store`, `log.txt` и прочие файлы, оставьте только служебные файлы, которые были упомянуты в первом пункте.
3. [Никаких `eval` и подобных функций](https://docs.keitaro.io/ru/landing-pages-and-offers/landing-page-local.html?h=eval).
4. [При загрузке дополнительных скриптов в include() и require() используется полный путь до файла (например, с dirname(__FILE__))](https://docs.keitaro.io/ru/landing-pages-and-offers/landing-page-local.html?h=require).
5. [Удалите теги `base` в вашем HTML коде](https://docs.keitaro.io/ru/landing-pages-and-offers/landing-page-local.html?h=require#%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D0%BA-%D0%BB%D0%B5%D0%BD%D0%B4%D0%B8%D0%BD%D0%B3%D0%B0%D0%BC).
6. ~~Удалите ВСЕ комментарии, они не нужны.~~
7. ~~Уберите все `<script>` в вашем HTML — мигрируйте их в JS файл, также уберите все `<style>` теги.~~
8. Уберите все файлы подключения стороних, локальных библиотек, которые возможно подключить прямо в html — это намного лучше.

    #### Было: 
    ```html
    <head>

        <link rel="stylesheet" type="text/css" href="css/bootstrap.css">

    </head>
    ```

    #### Стало: 
    ```html
    <head>
 
        <link
          href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
          rel="stylesheet"
          integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH"
          crossorigin="anonymous"
        /> 

    </head>
    ```
9.  ~~Все изображения — только локально.~~
    - ~~Никаких внешних ссылок на картинки. Все файлы должны храниться в папке `assets/images/` вашего лендинга.~~
    - ~~Все изображения должны быть конвертированы в формат **WebP** для ускорения загрузки и экономии трафика.~~ 
    ~~Онлайн-конвертер в WebP: [https://convertio.co/ru/webp-converter/](https://convertio.co/ru/webp-converter/)~~
        
