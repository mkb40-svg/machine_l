# Виртуальная лаборатория: классификация и кластеризация текстов

Учебный комплекс для направления «Компьютерная лингвистика»: 15 интерактивных HTML-лабораторий (анимация алгоритмов в браузере) и 15 практикумов в Google Colab (те же темы на текстах, scikit-learn).

## Состав

| № | Тема | Лаборатория (браузер) | Практикум (Colab) |
|---|---|---|---|
| 1 | Классификация и кластеризация | [`labs/lab01_basics.html`](labs/lab01_basics.html) | [`notebooks/01_basics.ipynb`](notebooks/01_basics.ipynb) |
| 2 | Подготовка наборов данных | [`labs/lab02_datasets.html`](labs/lab02_datasets.html) | [`notebooks/02_datasets.ipynb`](notebooks/02_datasets.ipynb) |
| 3 | Multiclass и multilabel | [`labs/lab03_multi.html`](labs/lab03_multi.html) | [`notebooks/03_multi.ipynb`](notebooks/03_multi.ipynb) |
| 4 | Линейные модели и границы | [`labs/lab04_linear.html`](labs/lab04_linear.html) | [`notebooks/04_linear.ipynb`](notebooks/04_linear.ipynb) |
| 5 | Градиентный спуск | [`labs/lab05_gradient.html`](labs/lab05_gradient.html) | [`notebooks/05_gradient.ipynb`](notebooks/05_gradient.ipynb) |
| 6 | Метод k ближайших соседей | [`labs/lab06_knn.html`](labs/lab06_knn.html) | [`notebooks/06_knn.ipynb`](notebooks/06_knn.ipynb) |
| 7 | Решающие деревья | [`labs/lab07_tree.html`](labs/lab07_tree.html) | [`notebooks/07_tree.ipynb`](notebooks/07_tree.ipynb) |
| 8 | Случайный лес | [`labs/lab08_forest.html`](labs/lab08_forest.html) | [`notebooks/08_forest.ipynb`](notebooks/08_forest.ipynb) |
| 9 | Подбор гиперпараметров | [`labs/lab09_hyperparams.html`](labs/lab09_hyperparams.html) | [`notebooks/09_hyperparams.ipynb`](notebooks/09_hyperparams.ipynb) |
| 10 | Дисбаланс классов | [`labs/lab10_imbalance.html`](labs/lab10_imbalance.html) | [`notebooks/10_imbalance.ipynb`](notebooks/10_imbalance.ipynb) |
| 11 | Расстояния, сходство, центроид | [`labs/lab11_distance.html`](labs/lab11_distance.html) | [`notebooks/11_distances.ipynb`](notebooks/11_distances.ipynb) |
| 12 | Алгоритм K-Means | [`labs/lab12_kmeans.html`](labs/lab12_kmeans.html) | [`notebooks/12_kmeans.ipynb`](notebooks/12_kmeans.ipynb) |
| 13 | Иерархическая кластеризация и DBSCAN | [`labs/lab13_hier_dbscan.html`](labs/lab13_hier_dbscan.html) | [`notebooks/13_hier_dbscan.ipynb`](notebooks/13_hier_dbscan.ipynb) |
| 14 | Оценка качества кластеризации | [`labs/lab14_quality.html`](labs/lab14_quality.html) | [`notebooks/14_quality.ipynb`](notebooks/14_quality.ipynb) |
| 15 | Тематическое моделирование (LDA) | [`labs/lab15_lda.html`](labs/lab15_lda.html) | [`notebooks/15_lda.ipynb`](notebooks/15_lda.ipynb) |

Дополнительно: `index.html` (оглавление), `.nojekyll`.

## Публикация на GitHub Pages

1. Создайте репозиторий и загрузите содержимое этой папки в корень ветки `main`.
2. Settings → Pages → Source: **Deploy from a branch**, ветка `main`, папка `/ (root)` → Save.
3. Через 1–2 минуты сайт откроется по адресу `https://<пользователь>.github.io/<репозиторий>/`.
4. На странице оглавления ссылки «Практикум в Colab» подставятся автоматически (предполагается ветка `main`).

Лаборатории не требуют сервера и внешних библиотек: каждый файл можно открыть двойным щелчком, положить на флешку или загрузить в Moodle.

## Практикумы в Colab

Откройте `notebooks/NN_*.ipynb` через ссылку со страницы-оглавления или по шаблону
`https://colab.research.google.com/github/<пользователь>/<репозиторий>/blob/main/notebooks/01_basics.ipynb`.

Каждый ноутбук самодостаточен: первая ячейка создаёт файл `common.py` (учебный корпус из 4 тем: спорт, политика, кулинария, технологии, и вспомогательные функции). Запускайте ячейки сверху вниз. Все ноутбуки проверены на scikit-learn 1.8 и выполняются за несколько секунд.

**Свой корпус.** Корпус по умолчанию шаблонный: он нужен, чтобы алгоритмы вели себя предсказуемо. Для реальной работы замените строку `df = make_corpus(...)` на
```python
df = pd.read_csv("texts.csv")   # столбцы: text, label
```
Для русских текстов полезны лемматизация (`pymorphy3`) и удаление стоп-слов.

## Замечания

- В лабораториях данные игрушечные (десятки или сотни точек): они иллюстрируют принцип работы алгоритма, а не точность на реальных корпусах.
- Границы решения для текстов показаны на 2D-проекции (аналог SVD); в настоящем пространстве признаков граница живёт в тысячах измерений.
- Лаборатория 15 запускает настоящий LDA (сэмплирование по Гиббсу) на корпусе из 12 лемматизированных документов.
