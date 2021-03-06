# Экзамен

>Разработать приложение, которое показывает погоду из данных открытых источников.

## Задания и критерии:

Код для первого пункта:

```bash
cd <ваш проект>
# 1. сохранить весь текущий прогресс, если такой имеется
# (git stash или git commit && git push)
# 2. Переключаемся в мастер и синхронизируемся с github
git checkout master
git pull origin master
# 3. для избежания проблем при деплое,
# стоит заранее удалить папку node_modules и файл package-lock.json
rm -rf node_modules && rm package-lock.json
# 4. обновить в корневом проекте react-scripts до 3.3.0
npm i -S react-scripts@3.3.0
# 5. создать проект в master ветке
git checkout -b exam
npx create-react-app exam
```

- [ ] В корневой папке проекта создать базовое приложение `exam` с помощью [CRA](https://github.com/facebook/create-react-app#quick-overview)
- [ ] Сверстать страницы и необходимые компоненты. Использовать стили
- [ ] Поиск погоды по названию города
- [ ] Выбор погоды по ID из списка доступных
- [ ] Выбор погоды по географическим координатам
- [ ] Использовать `React-router` для перехода между страницами
- [ ] Использовать `Redux` для построения хранилища данных приложения и взаимодействия с ним
- [ ] Задеплоить в решение `Travis CI`.
- [ ] Теория: Объяснить, почему были использованы те или иные инструменты, участки кода и механизмы при решении задачи (выполняется лично с преподавателем)
- [ ] Ревью: получить правки по коду и исправить их (получается лично у преподавателя и выполняется самостоятельно)

## Макеты

### Главная страница
![Список локаций](./1.jpeg)

* Первый элемент - это текущая геопозиция
* Все последующие элементы - хардкод избранных из полученного списка (про список id городов ниже)
* "Парящая" кнопка "+" - это действие "добавить город в список"
* Для каждого элемента выводятся основные погодные показатели (см. скриншот)

### Подробная страница локации
![Подробная страница локации](./2.jpeg)
* Подробная информация о погоде на 3 дня

### Иконки для состояния погоды (ключ `weather[n].icon` в `json`)
[Графика (картинки) для отображения погодных условий](https://openweathermap.org/weather-conditions)

## Информация по API

* Адрес: https://openweathermap.org/current
* Получить [API KEY](https://home.openweathermap.org/users/sign_up)
* Полученный `API KEY` использовать в поле `appid=<API KEY>` при отправке запросов

### `By city name`

Пример запроса: https://api.openweathermap.org/data/2.5/weather?q=London,uk&appid=b6907d289e10d714a6e88b30761fae22

### `By city ID`

Пример запроса: https://api.openweathermap.org/data/2.5/weather?id=2172797&appid=b6907d289e10d714a6e88b30761fae22
Для получения списка `ID` необходимо скачать [json](http://bulk.openweathermap.org/sample/city.list.json.gz), выбрать из него список "избранных" 5 локаций (ID и name) и захардкодить их в приложение.

### `By geographic coordinates`

Пример запроса: https://api.openweathermap.org/data/2.5/weather?lat=35&lon=139&appid=b6907d289e10d714a6e88b30761fae22

### Подробный прогноз погоды на несколько дней

Пример запроса: https://api.openweathermap.org/data/2.5/forecast?q=London,uk&appid=b6907d289e10d714a6e88b30761fae22

## Важно:

* Для сдачи экзамена необходимо создать `PR`, который должен включать в себя только проделанную работу.
* Пользоваться можно всем, чем угодно.
* Задавать вопросы можно и нужно.
* Если сидите над каким-то пунктом более 10 минут, не понимая, что делать - поднимайте руку, поможем.

## Бонус

Если с заданием получается справиться за время экзамена, то вы получаете +2 балла
