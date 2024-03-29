# Cinco video-translater

## Установка и использование
Пример использования приложения будет описан в [google colab](https://colab.research.google.com/drive/1MDOLKIosg7achXpSlHUdq1_Xu-ut1S1a?usp=sharing) 
Если вы планируете использовать локальную машину, необходимо будет создать [виртуальное окружение](https://pythonchik.ru/okruzhenie-i-pakety/virtualnoe-okruzhenie-python-venv) или докер образ, так как некоторые технологии используемые внутри могут требовать старые версии библиотек.

При первом запуске нам необходимо запустить ячейки установки зависимостей находящихся в разделе "основные импорты", это может занять какое-то время.

Затем запускаем ячейки относящиеся к "классы для взаимодействия"

Примерное время установки библиотек

```sh
!pip install TTS["all"] ~ 6 min
!pip install TTS["all"] ~ 4 min
В сумме 10 min
```

Если ваш вывод выглядит так, поздравляю можно приступать к использованию.

## Первые шаги
Для начала просто переведем наше первое видео.
Если вы в [google colab](https://colab.research.google.com/drive/1MDOLKIosg7achXpSlHUdq1_Xu-ut1S1a?usp=sharing), то вам достаточно выполнить следующую ячейку.
На локальной машине необходимо просто записать две переменные video_path и buffer_dir путь к видео для перевода и папка для буферных файлов(будет автоматически удалена в конце, эту настройку можно менять)

Запускаем все следующий ячейки - это классы с методами, обеспечивающие перевод на другой язык.
На ячейке  - 

```sh
from google.colab import files
uploaded = files.upload()
lang = input('Введите язык на который нужно превести')
video_path = list(uploaded.keys())[0]
buffer_dir = 'buffer'
```
После запуска, вписываем язык перевода и выбираем файл видео, которое мы хоитим сдублировать
После этого выполняем все остлаьные ячейки и после наблюдаем в папке проекта - файлы с новым сдублированным видео - result_video.mp4, а в файлах russia_text.txt и foreign_text.txt текст из видео на русском и в следущем перевод его на выбранный язык
