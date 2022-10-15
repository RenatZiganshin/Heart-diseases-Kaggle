# Heart diseases Kaggle competition

Решение задачи по предсказанию болезни сердца пациентов в рамках соревнования среди студентов Яндекс.Практикума на платформе Kaggle. Метрика оценки модели - ROC-AUC.

Ход выполнения работы представлен на схеме ниже.

![alt text](https://github.com/RenatZiganshin/Heart-diseases-Kaggle/blob/main/Screenshots/workspace.png)

После предобработки данных добавлен новый признак - произведение массы пациента на возраст, что увеличило точность моделей.
Анализ предсказаний различных типов моделей показал, что лучше всего с данной задачей справляются модели градиентного бустинга - *XGBoost*, *CatBoost*, *LightGBM*. Отмечено, что комбинация из их решений (среднее арифметическое параметра *predict_proba*) на валидационной выборке дает большее значение ROC-AUC, чем этих моделей по отдельности. На практике были проверены разные комбинаций моделей, наилучший результат показал именно ансамбль из решений моделей градиентного бустинга.

Выполнено повторное обучение этих трех моделей, но уже на полном датасете для увеличения качества обучения. После чего на проверку отправлена комбинация предсказаний моделей на тестовой выборке.

Такое решение показало значение ROC-AUC на Public Score 0.80876, на Private Score - 0.80412, что позволило занять первое место в соревновании.

![alt text](https://github.com/RenatZiganshin/Heart-diseases-Kaggle/blob/main/Screenshots/leadreboard.png)
