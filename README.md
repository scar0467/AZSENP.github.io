<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Карта АЗС</title>
    <script src="https://api-maps.yandex.ru/2.1/?lang=ru_RU" type="text/javascript"></script>
    <style>
        #map {
            width: 100%;
            height: 100vh;
        }
    </style>
</head>
<body>
    <div id="map"></div>
    <script type="text/javascript">
        ymaps.ready(init);

        function init() {
            var myMap = new ymaps.Map("map", {
                center: [55.751574, 37.573856], // Москва
                zoom: 10
            });

            // Пример данных для отображения АЗС
            var azsData = [
                { coords: [55.751574, 37.573856], name: "АЗС 1" },
                { coords: [55.761574, 37.583856], name: "АЗС 2" },
                { coords: [55.771574, 37.593856], name: "АЗС 3" }
            ];

            azsData.forEach(function(azs) {
                var placemark = new ymaps.Placemark(azs.coords, {
                    balloonContent: azs.name
                });

                myMap.geoObjects.add(placemark);
            });
        }
    </script>
</body>
</html>
