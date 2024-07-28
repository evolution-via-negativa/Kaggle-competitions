# Прогнозирование уровня риска во время беременности
[Проект](https://github.com/evolution-via-negativa/Portfolio/blob/main/%D0%9F%D1%80%D0%BE%D0%B3%D0%BD%D0%BE%D0%B7%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5%20%D1%83%D1%80%D0%BE%D0%B2%D0%BD%D1%8F%20%D1%80%D0%B8%D1%81%D0%BA%D0%B0%20%D0%B2%D0%BE%20%D0%B2%D1%80%D0%B5%D0%BC%D1%8F%20%D0%B1%D0%B5%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D0%B8/%D0%9F%D1%80%D0%BE%D0%B3%D0%BD%D0%BE%D0%B7%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5%20%D1%83%D1%80%D0%BE%D0%B2%D0%BD%D1%8F%20%D1%80%D0%B8%D1%81%D0%BA%D0%B0%20%D0%B2%D0%BE%20%D0%B2%D1%80%D0%B5%D0%BC%D1%8F%20%D0%B1%D0%B5%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D0%B8.ipynb)  
# Постановка задачи:
Необходимо спрогнозировать уровень риска во время беременности
# Навыки и инструменты:  
* **python**
* **numpy**
* **pandas**
* **matplotlib**
* **optuna**
* **sklearn.dummy.DummyClassifier**
* **sklearn.tree.DecisionTreeClassifier**
* **sklearn.ensemble.RandomForestClassifier**
* **lightgbm.LGBMClassifier**
# Общий вывод:
- после исследования и предобработки данных мы свели задачу прогнозирования уровня риска беременных к задаче порядковой классификации (`Ordinal сlassification`)
- мы обучили несколько моделей `OrdinalClassifier` (состоящих из классификаторов `DecisionTreeClassifier`, `RandomForestClassifier`, `LGBMClassifier`) с перебором гиперпараметров. Все они показали результаты прогнозирования лучше наивной модели
- в результате тестирования моделей на валидационной выборке лучше всех оказалась модель `OrdinalClassifier` состоящая из классификаторов `RandomForestClassifier`
- по результатам тестирования можно заметить, что все ошибки наилучшей модели по своим значениям не велики. Она никогда не путает уровень риска `low risk` с `high risk` и наоборот
