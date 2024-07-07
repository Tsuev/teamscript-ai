# Документация по запуску решения команды TeamScript

### 1. Скачайте файлы из гит репозитория

`git clone https://github.com/Tsuev/teamscript-ai.git`

### 2. Создайте докер образ

`docker build -t teamscript-app:latest .` 

Или любое другое название вместо teamscript-app

(Внимание! Это может занять относительное большое время)

### 3. Запустите докер образ

`docker run -d -p 8888:8888 --name teamscipt-container teamscript-app:latest`

### 4. Получение токена для доступа к Jupyter Notebook

`docker logs teamscript-container`
или
`docker logs [container-id]`

В логах найдите URL по которуму локально развернут Jupyter Notebook
Он должен выглядет следующим образом:

`http://127.0.0.1:8888/?token=tokenname12345`

### 5. Запустите Jupyter Notebook

Перейдите по адресу `http://127.0.0.1:8888/` или `localhost:8888`

Вставьте в окно логина свой токен как в примере выше - `tokenname12345`


### 6. Запустите скрипты из файла `pipeline.ipynb` по порядку

Результатом выполнения блоков кода будет создание файла `modelPredict.csv` в котором будут сохранены предскзаданные значения.


## Дополнительная информация 

### Просмотр контейнеров

`docker ps`

### Просмотр локальных образов

`docker images`

Будет полезно для просмотра собранных образов

### Остановка/удаление контейнера

`docker stop teamscipt-container`
`docker rm teamscipt-container`

### Файл примера вывода после запуска нейросети

`sample_submission.csv`