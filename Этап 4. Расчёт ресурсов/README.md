# Расчёт ресурсов
## Задача
Расчёт ресурсов (сетевой канал, HDD/SSD)
Расчёт ресурсов необходимо осуществлять на основе п.3 плана работы.
Каждую из основных сущностей (будущая таблица в СУБД) нужно будет всё-таки спроектировать на физическом уровне модели данных (примерный список очевидных полей в таблице с типами данных). Если у вас подразумевается хранение изображение, то вы должны выбрать его средний размер.
Далее необходимо рассчитать следующие базовые параметры:
1.	Число пользователей (мыслить порядками в миллионах);
2.	Число ключевых транзакций от пользователей п.1 в секунду (например, число загрузок фотографий на веб-сервер);
3.	Объём write и read-трафика по каждой ключевой транзакции в секунду (Кбит/сек, Мбит/сек);
4.	Объём хранилища (HDD и SSD) для хранения ключевых таблиц и BLOB данных на 1-3-5 лет вперёд (Гбайт, Тбайт);
5.	[Опционально] Расчёт объёма кеширования на 1-3-5 лет (Гбайт).
Важно: в расчёте не нужно учитывать избыточность компонентов и данных

## Выполнение расчёта ресурсов
1. Число пользователей 1000 в месяц
2. Read/Write -> Read Heavy -> 4:1
3. Допустим, что пользователь загружает 20 новых фото в месяц и просматривает их 80 раз в месяц = 100000 в месяц
4. 100000 / (30*24*3600) = 140 операций в час (2.3 фото в минуту)
5. Вес одного фото с метаданными и прочим для обычного пользователя = 5Мб.
Также максимальные размеры фото могут отличаться в зависи от вида учетной записи(тарифа).
Минимальный трафик - 200Кб/сек (Need 3G)
6. Время хранения фото: 1000 пользователей * 20 фото * 12 месяцев * 5 лет = 1200000 фото = 6 ТБ (без учета изображений высокого разрешения и прочего) = 10 ТБ в RAID5