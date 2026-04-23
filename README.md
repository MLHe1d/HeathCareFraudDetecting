# Healthcare Insurance Fraud Detection

## Project Goal

Identify key features of fraudulent insurance claims in the healthcare sector and, based on the findings, determine the most suitable model for detecting such operations.

## Methodology

1. Key features of fraudulent claims are identified through exploratory data analysis (EDA) using visualization tools from the matplotlib library.
2. Machine learning models are built based on the identified fraud indicators using the scikit-learn library.
3. Model quality is evaluated using Decision Tree visualization, feature importance visualization for Random Forest, and confusion matrix analysis.

## Key EDA Findings

1. A clear downward trend is observed in the approved-to-requested claim ratio as the requested amount increases. The majority of fraudulent claims are concentrated in provider segments B, C, and D.

![Chart 1](1.png)

2. A clear correlation is observed: more days between service and claim submission — less fraud.

![Chart 2](2.png)

3. The median requested amount is significantly higher in cases where the number of days between service and submission approaches zero, which naturally reflects the correlation between delay and fraud.

![Chart 3](3.png)

4. Scatter plots below show fraudulent claims in yellow and legitimate claims in purple.

![Chart 4](4.png)
![Chart 5](5.png)

### Identified Features of Fraudulent Claims

*Fraudulent claims in this dataset are characterized by a short delay between service delivery and claim submission. They also show a large gap between the requested insurance amount and the approved reimbursement, whereas legitimate claims tend to have a requested-to-approved ratio close to 1:1.*

## Project Structure

1. *preparing.ipynb* — EDA notebook for identifying key fraud indicators. Reflects the data exploration stage in the order the dataset was studied.
2. *DecisionTree.ipynb* — notebook with Decision Tree model results.
3. *RndmForest.ipynb* — notebook with Random Forest model results.
4. *sys.ipynb* — notebook for installing required libraries.

## Conclusions

1. Visual analysis identified approval_ratio < 0.75 as the key fraud indicator. The Decision Tree independently confirmed this threshold as the first and most significant split.
2. Both models produced similar results, explained by the synthetic nature of the data and the clear linear separability of classes across two features.
3. The model was trained on synthetic data with deliberately embedded fraud patterns. On real-world data, class boundaries would be less distinct, requiring more features and more careful handling of class imbalance.

---
---

# Проект по созданию моделей выявления фрода в сфере медицинского страхования

## Задача проекта

*Выявить основные признаки фродовых заявок в сфере медицинского страхования и на основании выявленных признаков определить наиболее подходящую модель для детектинга подобных операций.*

## Методология

1. Выявление основных признаков фродовых заявок проводится путём анализа приведённого датафрейма с использованием инструментов визуализации из библиотеки matplotlib.
2. Построение моделей машинного обучения на основе выявленных признаков мошенничества с использованием библиотеки scikit-learn.
3. Оценка качества моделей с помощью визуализации decision tree, визуализации features importance для random forest, построение confusion matrix для моделей.

## Ключевые находки из EDA

1. Наблюдаем чёткий тренд на снижение одобряемой доли страховой выплаты от запрашиваемой суммы при росте запрашиваемой суммы. При этом большая часть фродовых запросов сосредоточена в сегментах B, C, D.

![График 1](1.png)

2. Наблюдаем корреляцию: больше дней = меньше фрода.

![График 2](2.png)

3. Медианная запрошенная сумма значительно выше в случаях, где сумма дней между запросом и услугой стремится к минимуму. Что закономерно отражает корреляцию между количеством дней и фродом.

![График 3](3.png)

4. Точечные графики: жёлтым цветом отражены фродовые заявки, фиолетовым — заявки без маркера фрода.

![График 4](4.png)
![График 5](5.png)

### Выявлены следующие признаки для мошеннических заявок

*Для мошеннических операций в приведённом датасете характерна низкая задержка между оказанием услуги и подачей запроса. Для мошеннических заявок характерна большая разница между запрошенной страховой суммой и суммой, одобренной для возмещения, когда для обычных заявок отношение запрошенной суммы к одобренной ближе к пропорции 1:1.*

## Структура проекта

1. *preparing.ipynb* — ноутбук с исследованием данных для выявления основных признаков мошеннических операций. Отражает этап работы с данными перед их использованием. Здесь сохранён код в том порядке, в котором шло изучение датасета.
2. *DecisionTree.ipynb* — ноутбук с результатом предсказания модели DecisionTree.
3. *RndmForest.ipynb* — ноутбук с результатом предсказания модели RandomForest.
4. *sys.ipynb* — ноутбук для установки в окружение недостающих библиотек.

## Выводы

1. Визуальный анализ выявил порог approval_ratio < 0.75 как ключевой индикатор фрода. Decision Tree независимо подтвердил этот порог как первый и наиболее значимый сплит.
2. Обе модели показали схожий результат, что объясняется синтетической природой данных и чёткой разделимостью классов по двум признакам.
3. Модель обучена на синтетических данных с намеренно заложенными паттернами фрода. На реальных данных границы между классами будут размыты, потребуется больше признаков и более тщательная работа с дисбалансом.