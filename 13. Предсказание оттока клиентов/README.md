# 12. Предсказание оттока клиентов

### Цели проекта  

- Спрогнозировать отток клиентов мобильного оператора для планирования предиктивных мер (скидок, особых условий).  
Для выборки клиентов доступны персональные данные, информация о тарифах и договорах.  
- Построить модель со значением метрики качества ROC_AUC не меньше 0.85.  
Дополнительно зафиксировать accuracy модели.

### Задачи проекта  

1. Исследовательский анализ данных  
    - Загрузка данных  
    - Предобработка данных  
    - Анализ данных и отбор признаков  
2. Выбор и обучение модели
    - Логистическая регрессия  
    - Random Forest  
    - Градиентный бустинг (lightgbm)  
3. Анализ результатов предсказаний  

### Итоги

1. Проведён анализ признаков и выявлены следующие инсайты.   
   - с увеличением помесячных платежей кол-во ушедших клиентов увеличивается
   - в первые месяцы кол-во ушедших клиентов велико, однако со временем их кол-во уменьшается.
   - большая доля ушедших среди пользователелей пользующиеся безналичным расчетом
2. Обучены модели: LogisticRegression, RandomForestClassifier, LGBMClassifier.  
Наилучшее качество предсказаний достигнуто с моделью **LGBMClassifier**. **ROC_AUC = 0.91** на тестовой выборке.  
3. Наибольший вклад в предсказание модели вносят признаки:  
    - `duration_days` - количество дней, которое клиент пользуется сервисами
    - `MonthlyCharges` - ежемесячный платёж за услуги. Для ушедших пользователей этот показатель выше.
    - `TotalCharges` - общая сумма, которую клиент заплатил за всё время услуг
    
### Используемый стек инструментов

- python
- pandas
- numpy
- sklearn
- matplotlib
- seaborn
- lightgbm  
