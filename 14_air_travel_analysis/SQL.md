###Запрос №1. 
Найдем количество рейсов на каждой модели самолёта с вылетом в сентябре 2018 года. Назовем получившееся поле flights_amount и выведем его. Также напечатаем на экране поле model.


<SELECT 
    aircrafts.model,
    COUNT(flights.flight_id) AS flights_amount
FROM 
    flights 
    INNER JOIN aircrafts ON aircrafts.aircraft_code = flights.aircraft_code
WHERE
    EXTRACT(MONTH FROM flights.departure_time) = 9
GROUP BY
    model>

###Запрос №2. 
Посчитаем отправленные в сентябре рейсы самолётов следующих моделей:
- Boeing,
- Airbus,
- другие (“other”).
Назовем получившуюся переменную flights_amount и выведите её значение на экран.


<SELECT 
    CASE WHEN
             aircrafts.model LIKE '%Boeing%' THEN
             'Boeing'
         WHEN 
             aircrafts.model LIKE '%Airbus%' THEN
             'Airbus'
         ELSE
             'other'
         END AS modell,
    COUNT(flights.flight_id) AS flights_amount
FROM 
    flights 
    INNER JOIN aircrafts ON aircrafts.aircraft_code = flights.aircraft_code
WHERE
    EXTRACT(MONTH FROM flights.departure_time) = 9
GROUP BY
    modell>

###Запрос №3. 
Посчитаем среднее количество прибывающих рейсов в день для каждого города за август 2018 года. Назовем получившееся поле average_flights, вместе с ним выведем столбец city.
Порядок вывода столбцов:
- city,
- average_flights.


<SELECT
    cnt.city,
    AVG(cnt.count_flights) AS average_flights
FROM
    (SELECT
        airports.city AS city,
        EXTRACT(DAY FROM flights.arrival_time) AS day,
        COUNT(*) as count_flights
    FROM
        flights JOIN airports ON flights.arrival_airport = airports.airport_code
    WHERE
        EXTRACT(MONTH FROM flights.arrival_time) = 8
    GROUP BY
        airports.city,
        EXTRACT(DAY FROM flights.arrival_time)) AS cnt
GROUP BY
    cnt.city>

###Запрос №4. 
Установим фестивали, которые проходили с 23 июля по 30 сентября 2018 года в Москве и номер недели, в которую они проходили. Выведем название фестиваля festival_name и номер недели festival_week.


<SELECT
    festival_name,
    EXTRACT (WEEK FROM festival_date) AS festival_week
FROM
    festivals
WHERE
    festival_city = 'Москва' AND
    festival_date BETWEEN '2018-07-23' AND '2018-09-30'>

###Запрос №5. 
Для каждой недели с 23 июля по 30 сентября 2018 года посчитаем билеты, которые купили на рейсы в Москву (номер недели week_number и количество билетов ticket_amount). Получим таблицу:
- с количеством купленных за неделю билетов;
- отметкой, проходил ли в эту неделю фестиваль;
- названием фестиваля festival_name;
- номером недели week_number.
Порядок вывода столбцов:
- week_number
- ticket_amount
- festival_week
- festival_name


<SELECT 
    T.week_number,
    T.ticket_amount,
    T.festival_week,
    T.festival_name
FROM 
(
(SELECT
        EXTRACT (week FROM flights.departure_time) AS week_number,
        COUNT(ticket_flights.ticket_no) AS ticket_amount
    FROM
        airports
    INNER JOIN
        flights
    ON
        airports.airport_code = flights.arrival_airport
    INNER JOIN
        ticket_flights
    ON
        flights.flight_id = ticket_flights.flight_id
    WHERE
        airports.city = 'Москва'
        AND CAST(flights.departure_time AS date) BETWEEN '2018-07-23' AND '2018-09-30'
    GROUP BY
        week_number
) t
LEFT JOIN 
(SELECT
        festival_name,
        EXTRACT (week FROM festivals.festival_date) AS festival_week
    FROM
        festivals
    WHERE
        festival_city = 'Москва'
      AND CAST(festivals.festival_date AS date) BETWEEN '2018-07-23' AND '2018-09-30'
) t2 
ON 
    t.week_number = t2.festival_week
) AS T>