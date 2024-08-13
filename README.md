### Задание 1
#### Условие
- Вам нужно разделить проект Mesto на несколько микрофронтендов. Самостоятельно решите, какой фреймворк будете использовать, — Module Federation или Single SPA

#### Решение
1. В данном задании использован фреймворк Module Federation из-за его простоты и потому что на данном этапе проекта не подразумевается использование разных технологий в микрофронтендах
2. В качестве микрофронтендов выделены следующие функции приложения:
- приложение для регистрации и входа
- Список мест (карточки) - добавление, удаление, просотр фото. управление лайками под фото
- Профиль - просмотр и редактирование профиля пользователя
- Общие элементы приложения - хэдер, футер и т.д.

> Для запуска необходимо перейти в директорию frontend и выполнить команду npm install и npm start. Хост будет запущен по адресу http://localhost:3000/

### Задание 2
#### Условие
- Декомпозировать монолитное бэкенд приложение на микросервисы, сохраняя консистентность приложения

#### Решение
[Ссылка на схему](Сервис%20управления%20торговыми%20площадками.%20АИС.drawio)

Сервисы:
- Api Gateway - входная точка в систему
- Сервис пользователей - сервис по хранению и обработке информации о пользователях.
- Сервис товаров и Услуг - товары и услуги и цены. выполняет поиск, добавление, редактирование товаров и услуг.
- Сервис ауциона - Создание аукционов и обработка заявок на участие.
- Сервис платежей - обработка платежей. Для проведения платежей выполняется вызов АПИ сторонних платежных систем.
- Сервис ТП - запросы в техническую поддержку.
- Сервис апелляций - обработка апелляций.
- Сервис заказов - заказы.
- Сервис отчетов - отчеты по заказам и пользователям. Все полученные данные хранятся в БД. Отчеты формируются по запросу потребителя
- Сервис нотификаций - Получает события из шины данных и отправляет уведомления потребителям.
- Шина данных (Kafka) - осуществляет коммуникацию между сервисами.
