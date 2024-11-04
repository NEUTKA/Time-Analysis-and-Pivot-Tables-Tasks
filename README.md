# Урок 5: Время и сводные таблицы

## Задание 1
Имеются следующие данные о транзакциях в период с 01.12.2010 по 12.09.2011:

- **InvoiceNo** — номер транзакции
- **StockCode** — код товара
- **Description** — описание товара
- **Quantity** — количество единиц товара, добавленных в заказ
- **InvoiceDate** — дата транзакции
- **UnitPrice** — цена за единицу товара
- **CustomerID** — id клиента
- **Country** — страна, где проживает клиент

В данной задаче ссылка для считывания данных лежит в переменной `path_to_file`.
- Импортируйте `pandas` и прочитайте данные с кодировкой `ISO-8859-1`.
- Запишите полученный датафрейм в переменную `retail`, а названия колонок сохраните в переменную `retail_columns`.

## Задание 2
- Проверьте, встречаются ли в данных повторяющиеся наблюдения, и укажите их количество.
- Если дубликаты есть, удалите их из `retail`.

## Задание 3
Данные содержат записи как об успешных транзакциях, так и об отменённых. Если пользователь отменил заказ, в начале номера транзакции (`InvoiceNo`) ставится "C" (canceled).

- Определите, сколько всего транзакций отменили пользователи.
- Считайте, что каждая строка - это отдельная транзакция.

## Задание 4
Отфильтруйте данные и оставьте в `retail` только те заказы, где `Quantity > 0`.

- Укажите число оставшихся строк.

## Задание 5
- Посчитайте число заказов для каждого пользователя (`CustomerID`) из Германии (`Germany`).
- Оставьте только тех, кто совершил более `N` транзакций (`InvoiceNo`), где `N` – это 80-й процентиль.
- Запишите полученные `id` пользователей в переменную `germany_top` (только `id`, без других данных).

Примечание: отфильтрованные данные находятся в `retail`. Для каждого заказа может быть более одной строки.

## Задание 6
Используя объект с `id` пользователей (`germany_top`), отфильтруйте наблюдения, оставив только записи по интересующим нас пользователям.

- Запишите результирующий датафрейм в `top_retail_germany`.

Примечание: датафрейм с данными — `retail`, нужные `id` пользователей — `germany_top`.

## Задание 7
Сгруппируйте `top_retail_germany` по коду товара (`StockCode`).

- Определите, какой из продуктов добавляли в корзину чаще всего, кроме товара с кодом "POST".

Примечание: одним заказом считается единоразовая покупка любого количества товара, т.е. без учета `Quantity`.

## Задание 8
Вернитесь к анализу полного набора данных `retail`.

- Создайте колонку `Revenue` с суммой покупки, используя `Quantity` и `UnitPrice`.

Примечание: отфильтрованные данные находятся в `retail`.

## Задание 9
Для каждой транзакции (`InvoiceNo`) посчитайте финальную сумму заказа.

- В качестве ответа укажите топ-5 транзакций (`InvoiceNo`) по сумме заказа (через запятую с пробелом и в порядке убывания `TotalRevenue`).