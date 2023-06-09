# Прогнозирование уровня сложности фильмов на английском языке

## Описание проекта
Просмотр фильмов на изучаемом языке помогает прокачать знания. При этом важно выбрать фильм, который подходит по уровню сложности.
Предоставлен датасет с выборкой фильмов и уровнем сложности, файлы субтитров в формате .srt

## Задача
Разработать ML модель для определения уровня сложности англоязычных фильмов.

## Краткое описание исследования
- текст очищен от тегов, дополнительных символов
- проведена токенизация, удалены стоп-слова
- использована лемматизация, слова приведены к начальной форме
- добавлены дополнительные признаки - общая продолжительность субтитров и средняя продолжительность одного субтитра
- каждый субтитр разбит на 3 части для увеличения количества наблюдений и повышения качества предсказания модели
- использованы различные способы векторизации - bag of words, TF-IDF и встроенный в модель Catboost.
- проведено обучение моделей на обучающей выборке с использованием кросс-валидации
- качество лучших моделей проверено на тестовой выборке.

### Рассмотрены модели:
- LogisticRegressionCV с использованием векторизации bag of words и TF-IDF
- Catboost с использованием векторизации bag of words и TF-IDF, а также с использованием встроенного средства.

## Результаты
Выбрана модель Catboost с использованием встроенного средства векторизации

Результаты Catboost на кросс-валидации: 
- balanced accuracy 0.86 (+/- 0.03)

Результаты Catboost на тестовой выборке:
- balanced accuracy: 0.9073
- F1 score micro: 0.8944