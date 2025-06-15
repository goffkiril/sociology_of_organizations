# Детекция моральной легитимации в стратегиях университетов

Данный репозиторий содержит материалы проекта по автоматическому выявлению **моральной легитимации** в стратегических документах университетов с использованием методов обработки естественного языка и трансформеров.

## 📁 Структура проекта

### 📂 Корневая директория

- `1_moral_legitimicy.ipynb`  
  Ноутбук для препроцессинга и аннотации стратегий университетов.

- `2_sft_model.ipynb`  
  Основной ноутбук с реализацией обучения и оценки классификатора на базе `facebook/roberta-base` для бинарной классификации предложений.

- `moral_legitimicy_annotated.csv`  
  Размеченный датасет из 1670 предложений, содержащих бинарную метку (`0` или `1`), указывающую наличие моральной легитимации.

- `moral_legitimacy_misclassified.csv`  
  Набор предложений, где модель допустила ошибки классификации (ложноположительные и ложноотрицательные срабатывания). Используется для анализа типичных ошибок.

- `manual_test_0.csv`, `manual_test_1.csv`  
  Ручной тест: выборки предложений, классифицированных моделью как `0` и `1`, соответственно, для дальнейшей проверки качества.

---

### 📂 Папка `Стратегии`

Содержит **20 стратегических документов университетов** в формате PDF. Эти документы легли в основу корпуса, из которого извлекались предложения для разметки и обучения модели.

Примеры университетов:
- Bocconi University  
- Cape Town University  
- Stanford University  
- University of Tokyo  
- London School of Economics  
и др.

Все документы получены с официальных сайтов вузов и отражают их стратегическое позиционирование, миссии и ценности.

---

## 🔍 Описание проекта

Проект:
- Исследует понятие **моральной легитимации** в рамках институциональной теории (Suchman, 1995)
- Формирует размеченную выборку предложений из стратегий университетов
- Обучает легковесный классификатор `roberta-base` на задачу бинарной классификации
- Выполняет количественную и качественную оценку результатов (F1 ≈ 0.83)
- Проводит анализ ошибок модели

Подробная методология, теоретическое обоснование и библиография представлены в сопровождающем эссе.

---

## 📚 Использованная литература

- Suchman, M. C. (1995). *Managing legitimacy: Strategic and institutional approaches*. Academy of Management Review, 20(3), 571–610.  
- Meyer, J. W., & Rowan, B. (1977). *Institutionalized organizations: Formal structure as myth and ceremony*. American Journal of Sociology, 83(2), 340–363.  
- DiMaggio, P. J., & Powell, W. W. (1983). *The iron cage revisited: Institutional isomorphism and collective rationality in organizational fields*. American Sociological Review, 48(2), 147–160.  
- Devlin, J. et al. (2019). *BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding*. NAACL-HLT.  
- Kowsari, K. et al. (2019). *Text classification algorithms: A survey*. Information, 10(4), 150.  
- Lima, M. A. et al. (2020). *Strategy or legitimacy? Analysis of the role of institutional development plans in Brazilian universities*. Brazilian Business Review, 17(1), 66–96.

---

## 🧪 Зависимости

- Python 3.10+
- `transformers`, `datasets`, `torch`, `scikit-learn`, `pandas`, `matplotlib`, `nltk`
