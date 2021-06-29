# Проекты, выполненные во время обучения в Яндекс.Практикуме по специальности "Специалист Data Science".


| Название проекта | Описание | Выводы | Используемые библиотеки | 
| :---------------------- | :---------------------- | :---------------------- | :---------------------- |
| [1. Исследование музыкальных предпочтений](01_music_preferences) | Сравнение предпочтений пользователей Яндекс.Музыки из Москвы и Санкт-Петербурга в зависимости от времени (утро и вечер) и дня недели (понедельник, среда, пятница)| Жители Москвы и Санкт-Петербурга сходятся в музыкальных предпочтениях: на 1 месте ожидаемо популярная музыка. День недели не влияет на прослушиваемые жанры. В Москве больше слушают в начале и в конце недели, в Петербурге - в середине.| *pandas* |
| [2. Исследование надежности заемщиков](02_reliability_of_borrowers) | Исследование верояности того, что клиент банка просрочит платеж по кредиту. Анализ влияния на просрочку семейного положения, количества детей, месячного дохода и цели взятия кредита. | Ни один из анализируемых параметров не влияет на вероятность внесения платежа по кредиту в срок. В срок платеж по кредиту вносят 9 из 10 клиентов банка. | *pandas*, *pymystem3*, *collections* |
| [3. Исследование стоимости недвижимости](03_apartment_price) | Исследование цен на недвижимость в Санкт-Петербурге и Ленинградской области. Анализ влияния различных параметров на стоимость жилья. Выделение категории квартир, относящихся к локации "центр города" и сравнение их с общим объемом квартир. | Больше всего на стоимость жилья влияет желая площадь. В качестве категории жилья "в центр города" установлена площадь радиусом 7 км. Сформулированы дополнительные требования к данным для более "чистого" анализа. | *pandas*, *numpy*, *matplotlib.pyplot*, *seaborn*, *IPython.display*, *warnings* |
| [4. Сравнение тарифов оператора сотовой связи](04_prospective_tariff) | Исследование дпнных об абонентах сотового оператора. Ответ на вопрос, какой из тарифов приносит больше прибыли компании. Проверка статистических гипотез с использованием p-значения и метода оценки распределения t-критерием Стьюдента. | Определили, что наибольший вклад в общий доход оператора - платежи за услуги сверх лимитов пакета (основные платежи по абонентской плате на 2-м месте). Средняя прибыль для двух тарифов компании а). различается, б). не зависит от региона.  | *pandas*, *numpy*, *matplotlib.pyplot*, *seaborn*, *math*, *scipy* |
| [5. Исследование рынка видеоигр](05_video_game_market) | Определение закономерностей, влияющих на успех продажи видеоигр. Анализ данных по жанрам, игровым платформам и регионам. Определение типичного геймера для каждого региона. Формирование стратегии рекламной компании на следующий год на основе полученных результатов. Проверка статистических гипотез с использованием p-значения и метода оценки распределения t-критерием Стьюдента. | Игровое сообщество разделено на восточное и западное, предпочтения которых значительно различаются. Оценки игроков и критиков фактически не влияют на продажи. На пике популярности Playstation 4, на втором месте Xbox One. | *pandas*, *numpy*, *matplotlib.pyplot*, *seaborn*, *math*, *scipy* |
| [6. Рекомендация тарифов с использованием машинного обучения](06_recommendation _of_tariffs_ml) | Построение модели машинного обучения, решающей задачу классификации: подбор наиболее подходящего тарифа для пользователя на основании его стиля использования услуг оператора. | Лучшей моделью показал себя RandomForestClassifier, accuracy = 0.81 | *pandas*, *time*, *tqdm*, *sklearn* |
| [7. Прогнозирование оттока клиентов банка](07_outflow_of_bank_customers_sl) | Построение модели машинного обучения, решающей задачу классификации: ответ на вопрос, относится ли клиент банка к категории тех, кто в ближайшее время может отказаться от услуг банка. | RandomForestClassifier дает результат f1_score = 0.61. При этом показатель полноты составляет 0.69, точности - 0.53, что согласуется с поставленной задачей. | *pandas*, *numpy*, *math*, *sklearn*, *random*, *matplotlib.pyplot*, *seaborn* |
| [8. Выбор региона для разработки нефтедобывающей компанией](08_location_for_the_well) | Построение модели машинного обучения, решающей задачу регрессии: в каком из трех регионов, по которым имеются данные, наиболее высокая потенциальная прибыльность начала нефтяных разработок и наименьшие риски финансовых потерь. | Для региона №1 риск получения убытка составляет 0.3% Среднее значение прибыли - 528 млн. руб. Границы 95% доверительного интервала: от 123 млн. до 925 млн. | *pandas*, *numpy*, *math*, *sklearn* |
| [9. Предсказание коэффициента восстановления золота из золотосодержащей руды](09_ml_in_the_gold_mining_industry) | Подготовка прототипа модели машинного обучения, решающей задачу регрессии: предсказание на основании имеющихся данных коэффициента восстановления золота из золотосодержащей руды. Результат - оптимизация производства, отказ от запуска производственного процесса очистки руды с убыточными характеристиками. | Для RandomForestRegressor значение метрики sMAPE = 9.91 | *pandas*, *numpy*, *sklearn*, *matplotlib.pyplot*, *seaborn* |
| [10. Защита персональных данных](10_data_encryption) | Разработка метода преобразования персональных данных клиентов страховой компании (шифрования) без потери связей между данными методами линейной алгебры (операции с векторами). Получение зашифрованного датасета, показывающего результат предсказаний модели, равный предсказаниям на оригинальных данных. | Для шифрования использовали операцию матричного умножения искомой матрицы на квадратную матрицу случайных чисел размерности количества признаков. | *pandas*, *numpy*, *sklearn* |
| [11. Предсказание стоимости автомобилей](11_cost_of_cars) | Построение модели машинного обучения, решающей задачу регрессии: предсказание стоимости автомобиля с пробегом на основании его технических характеристик и данных об эксплуатации. | По результатам обучения моделей RandomForest немного точнее, но в разы дольше обучается по сравнению с LightGBM. | *pandas*, *numpy*, *matplotlib.pyplot*, *lightgbm*, *sklearn*, *datetime* |
| [12. Предсказание заказов такси в аэропорту](12_time_series_in_taxi_orders) | Работа с временными рядами. Построение модели машинного обучения, предсказывающей ожидаемое количество заказов такси в аэропорту на следующий час. | Ансамблевая модель RandomForestRegressor показала меньшее значение среднеквадратической ошибки, чем линейная регрессия. | *pandas*, *numpy*, *matplotlib.pyplot*, *sklearn*, *datetime*, *statsmodels.tsa.seasonal* |
| [13. Идентификация "токсичных" комментариев](13_toxic_comments) | Построение модели машинного обучения на корпусе текстов, решающей задачу классификации: отнесение комментариев к допустимым для публикации и к требующим модерации. | В задаче машинного обучения на текстах лучший результат показала модель логистической регрессии. F1_score = 0.755 | *pandas*, *numpy*, *sklearn*, *time*, *re*, *nltk* |
| [14. Аналитика авиакомпании. Работа с базами данных SQL](14_air_travel_analysis) | Получение данных посредством запросов на языке структурированных запросов SQL. Анализ полученных данных на предмет факторов, влияющих на количество прибывающих рейсов самолетов в аэропорты разных городов. | Количество прибывающих в город рейсов находится в прямой зависимости от количества людей, проживающих в городе. Самой частой модели самолета в рейсах соответствует минимальный пассажиропоток (ввиду низкой пассажировместимости). | *pandas*, *numpy*, *matplotlib.pyplot*, *seaborn*, *SQL* |
| [15. Определние возраста покупателей магазина по фото](15_computer_vision) | Обучение модели ResNet50 для выполнения задачи компьютерного зрения. | Средняя абсолютная ошибка модели составляет 6 лет. Достаточно для рекомендаций товаров возрастным категориям покупателей, недостаточно для определения соответствия покупателя категории "совершеннолетние". | *pandas*, *numpy*, *PIL*, *matplotlib.pyplot*, *tensorflow.keras* |
| [16. Финальный проект]() | ------ | ------ |
