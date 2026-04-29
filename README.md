# Django XML/JSON Recipes with Calendar

Учебный Django-проект для работы с рецептами в форматах XML и JSON.

## Что реализовано

- ввод рецепта через HTML-форму
- валидация формы
- календарь на странице создания рецепта
- сохранение рецепта в XML
- дополнительное сохранение рецепта в JSON
- загрузка XML и JSON на сервер
- безопасная генерация имени файла
- валидация загружаемого файла
- автоматическое удаление невалидного файла
- вывод всех XML-файлов на отдельной странице
- сообщение, если XML-файлов нет
- экспорт всех XML-рецептов в единый XML
- экспорт всех XML-рецептов в единый JSON
- удобный запуск в Visual Studio Code

## Какую папку открывать в Visual Studio Code

Открывайте папку:

`django_xml_json_recipes_calendar`

Именно в ней находятся:
- `manage.py`
- `requirements.txt`
- `.vscode/`
- `recipes/`
- `recipe_portal/`

## Быстрый запуск

### 1. Открыть проект в VS Code
**File -> Open Folder...**  
Выбрать папку `django_xml_json_recipes_calendar`

### 2. Создать виртуальное окружение

#### Windows
```bash
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe manage.py migrate
.\.venv\Scripts\python.exe manage.py runserver
python -m venv .venv
.venv\Scripts\activate
```

#### Linux / macOS
```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Установить зависимости
```bash
pip install -r requirements.txt
```

### 4. Применить миграции
```bash
python manage.py migrate
```

### 5. Запустить сервер
```bash
python manage.py runserver
```

### 6. Открыть сайт
`http://127.0.0.1:8000/`

## Основные страницы

- `/` — создание рецепта
- `/upload/` — загрузка XML/JSON файла
- `/library/` — библиотека файлов
- `/export/xml/` — скачать общий XML
- `/export/json/` — скачать общий JSON

## Где лежат файлы

- XML: `data/xml/`
- JSON: `data/json/`

## Календарь

На странице создания рецепта есть поле **Дата приготовления**.
Оно реализовано как HTML5-календарь через поле:

```python
forms.DateField(widget=forms.DateInput(attrs={"type": "date"}))
```

## Проверка проекта

```bash
python manage.py check
python manage.py migrate
```
