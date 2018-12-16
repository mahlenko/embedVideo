# Адаптивное использование YouTube видео (desktop/mobile)
Быстрая вставка видео плеера YouTube без замедления загрузки страницы.
Вместо плеера на страницу будет загружено превью, с кнопкой просмотра видео, а
уже по клику на кнопку загрузиться плеер YouTube.

По-умолчанию поддерживает адаптивную загрузку: так как размер изображения (превью)
определяется автоматически, то при просмотре страницы с мобильных устройств, превью
будет определено под мобильный экран.

## Инструкция
Скачайте архив с Github или использовуйте Bower: ```bower install jquery-embed-video```

Добавьте контейнеры для ваших видео используя следующий код:
```
<-- Видео будет автоматически проиграно -->
<div class="embed-youtube" data-id="{ID VIDEO YOUTUBE}" data-autoplay="1" width="500" height="280"></div>

<-- Будет использована альтернативная обложка и автоматическое проигрывание видеоролика -->
<div class="embed-youtube" data-id="{ID VIDEO YOUTUBE}" data-image-play-container="{URL IMAGE}" data-autoplay="1" width="600" height="480"></div>
```

Добавьте скрипт перед закрывающим тегом ```</body>```
```
<script type="text/javascript" src="{path}/{to}/{files}/jquery.embedVideo.min.js"></script>
<script type="text/javascript">
    $('.embed-youtube').embedVideo({
        /**
         * Параметры плагина + доступные параметры проигрывателя (также их можно передать через [data-*] конкретного контейнера)
         * https://developers.google.com/youtube/player_parameters
         */
    });
</script>
```

Установка подразумевает, что вы уже **используете jQuery**.

## Параметры 
Обязательными является только {ID видео}, который удобнее задать в контейнере.

| [data-*]   | options   | доступные значения | описание |
|----------| --------- | ------------------ | -------- |
| id | id | {string} | ID видео |
| size-preview | sizePreview | default, mqdefault, hqdefault, sddefault, maxresdefault | Размер изображения превью, генерируемых YouTube. |
| auto-size-preview | autoSizePreview | **true**, false | Определять автоматически размер превью, исходя из размеров контейнера. |
| alternative-cover | alternativeCover | {string} | Ссылка на альтернативную обложку превью. |
| image-play-container | imagePlayContainer | {string} тег | HTML тег кнопки "play" на превью. По-умолчанию SVG иконка. Можно заменить на собственную иконку SVG или IMG. |
| image-play-opacity | imagePlayOpacity | 0 - 1 (по-умолчанию **0.85**) | Прозрачность кнопки "play" если задана, будет заметна анимация при наведении на контейнер с видео. |