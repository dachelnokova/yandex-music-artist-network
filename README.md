# yandex-music-artist-network
Парсер для сбора информации о музыкантах и похожих на них музыкантах с платформы Яндекс.Музыка  


## Особенности
* Cбор информации об артистах, включая имя, ID и URL изображения,
* Извлечение артистов со страницы жанра (например, [рок]([url](https://music.yandex.ru/genre/русский%20рок/artists)))
* Извлечение списка похожих артистов для каждого исполнителя из вкладки ["Похожее"]([url](https://music.yandex.ru/artist/4623000/similar)),
* Сохранение данных в текстовый файл для дальнейшего анализа.


## Файлы
* **yandex_music_artist_scraper.ipynb** : Jupyter Notebook с кодом парсера  
* **artist_data.txt**: Текстовый файл, содержащий собранные с помощью парсера данные об артистах. Собрана информация о 5915 музыкантах следующих жанров:
  * [местная инди-музыка (≈1300)]([url](https://music.yandex.ru/genre/местная%20инди-музыка/artists)),
  * [русский рок (≈1300)]([url](https://music.yandex.ru/genre/русский%20рок/artists)),
  * [русская поп-музыка (≈1300)]([url](https://music.yandex.ru/genre/русская%20поп-музыка/artists)),
  * [русский рэп (≈1300)]([url](https://music.yandex.ru/genre/русский%20рэп/artists)),
  * [русская эстрада (≈700)]([url](https://music.yandex.ru/genre/русская%20эстрада/artists)). 


## Структура данных
Каждая запись в artist_data.txt представляет собой словарь Python со следующей структурой:  
*{
    "artist_name": "Имя артиста",
    "artist_image_url": "URL изображения артиста",
    "artist_id": "ID артиста",
    "similar_artists": [
        {
            "artist_name": "Имя похожего артиста",
            "artist_image_url": "URL изображения похожего артиста",
            "artist_id": "ID похожего артиста"
        },
        ...
    ]
}*

## Датасеты для создания графа
artist_graph.csv – столбцы: artist_id, similar_artists_id (список id похожих исполнителей)
artists_params.csv – столбцы: artist_id, artist_name, artist_image_url,	genre


## Примечание
Парсер разработан исключительно в образовательных целях.
