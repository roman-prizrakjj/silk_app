# Пользовательская документация GoSilk Uploader

## Введение

GoSilk Uploader - это приложение, предназначенное для загрузки музыкальных релизов на платформу Gosilk и отправку релизов партнерам. Это руководство поможет вам разобраться с основными функциями и возможностями приложения, а также подскажет, как эффективно работать с программой для загрузки ваших музыкальных релизов.

### Установка на macOS

1. Скачайте DMG-файл установщика
2. Откройте DMG-файл и перетащите приложение GoSilk Uploader в папку Applications
3. При первом запуске может потребоваться разрешение на запуск приложения из неизвестного источника:
   - Откройте "Системные настройки" > "Безопасность и конфиденциальность"
   - Нажмите "Подтвердить разрешение" для GoSilk Uploader
4. Запустите приложение из папки Applications или через Launchpad

### Запуск программы

При запуске программа требует предустановленный пароль выданный менеджерам:

![1748539470296](image/USER_DOCUMENTATION/1748539470296.png)

## Интерфейс пользователя

Скриншоты здесь: https://drive.google.com/drive/folders/1PkF5SlnrxzSaPE9t77GwuzoYSyVc5uYG?usp=sharing

Интерфейс GoSilk Uploader разделен на несколько основных секций:

### Меню

![1748539562206](image/USER_DOCUMENTATION/1748539562206.png)

![1748555999455](image/USER_DOCUMENTATION/1748555999455.png)

Меню позволяет переключаться между различными режимами работы:

- **Загрузка релизов**: Основной режим для загрузки новых релизов
- **Аналитика:** Краткие сведение о сверке названий из таблицы с названиями файлов в пап

  ![1748556064961](image/USER_DOCUMENTATION/1748556064961.png)
- **Настройки**: Настройки подключения к API и другие параметры приложения

  ![1748556221657](image/USER_DOCUMENTATION/1748556221657.png)
- **Помощь**: Инструкция по использованию ПО и решению возможных ошибок

  ![1748556161868](image/USER_DOCUMENTATION/1748556161868.png)

### Панель инструментов

В центральной части экрана находится панель инструментов с кнопками для выполнения основных действий:

- **Выбрать Excel-файл**: Загрузка Excel-файла с метаданными релизов
- **Выбрать директорию**: Выбор папки с аудиофайлами и обложкой для загрузки
- **Проверить файлы**: Проверка соответствия файлов требованиям и сопоставление с метаданными
- **Загрузить релизы**: Загрузка проверенных файлов на платформу
- **Отправить на FTP**: Отправка загруженных релизов на FTP партнеров

### Рабочая область

Основная часть интерфейса, где отображается информация о релизах, результаты проверок и статус загрузки.

## Основные функции и модули

### 1. Подготовка Excel-файла с метаданными

Для успешной загрузки релизов необходимо подготовить Excel-файл с метаданными. Файл должен иметь следующую структуру:

| Колонка | Содержимое             | Описание                                                                                                               |
| -------------- | -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| A              | Имя файла трека     | Полное имя файла с расширением (например,`Artist - Track Name.wav`)                        |
| B              | Имя файла обложки | Полное имя файла с расширением (например,`Cover.jpg`)                                      |
| C              | UPC                              | Уникальный код продукта                                                                                   |
| D              | ISRC                             | Международный стандартный код записи                                                          |
| E              | Чистое имя трека   | Название трека без дополнительной информации                                           |
| F              | Жанр                         | Основной музыкальный жанр (по умолчанию "Pop")                                               |
| G              | Поджанр                   | Дополнительный жанр                                                                                          |
| H              | Имя релиза              | Название всего релиза                                                                                       |
| I              | Исполнитель           | Основной исполнитель                                                                                        |
| J              | Фиты релиза            | Приглашенные исполнители на всем релизе                                                     |
| K              | (не используется)  | -                                                                                                                              |
| L              | Фиты трека              | Приглашенные исполнители на конкретном треке                                           |
| M              | Композитор             | Автор музыки                                                                                                        |
| N              | Автор текста          | Автор слов                                                                                                            |
| O              | Explicit                         | Пометка "Да"/"Нет"/"True"/"False"/1/0 для содержания с возрастным ограничением |
| P              | Язык трека              | Основной язык текста трека                                                                              |
| Q              | Лейбл                       | Название лейбла                                                                                                  |
| R              | Платформы               | Список платформ через запятую или "All" для всех                                           |
| S              | Регионы                   | Список кодов стран через запятую или "WW"/"All" для всех                                 |
| T              | Дата публикации    | Дата первой публикации в формате ДД/ММ/ГГГГ                                                |
| U              | Партнерский код    | Код партнера (если есть)                                                                                    |

#### Рекомендации по подготовке Excel-файла:

- Используйте точные имена файлов с расширениями
- Один трек на одну строку
- Для релиза с несколькими треками используйте одинаковое название релиза и UPC
- Первая строка должна содержать заголовки (они будут пропущены при загрузке)

### 2. Загрузка файлов и метаданных

#### Шаг 1: Выбор Excel-файла

1. Нажмите кнопку "Выбрать Excel-файл"
2. В открывшемся окне выберите подготовленный Excel-файл с метаданными
3. После загрузки файла вы увидите список релизов, извлеченных из Excel

#### Шаг 2: Выбор папки с файлами

1. Нажмите кнопку "Выбрать директорию"
2. В открывшемся диалоговом окне выберите папку содержащую аудиотреки и обложки для загрузки
3. После выбора директории она будут отображена в интерфейсе

### 3. Проверка файлов

После выбора всех необходимых файлов нажмите кнопку "Проверить файлы". Система выполнит следующие проверки:

1. **Соответствие аудиофайлов и обложек метаданным из Excel**:

   - Проверка наличия всех необходимых файлов
   - Сопоставление имен файлов с данными из Excel
2. **Проверка качества аудиофайлов**:

   - Формат файлов (WAV, FLAC, AIFF)
3. **Проверка обложек**:

   - Формат файлов (JPG, PNG)
   - Размер (минимум 3000x3000 пикселей)
   - Соотношение сторон (1:1 - квадратное изображение)

Результаты проверки будут отображены в отчете с указанием:

- Успешно проверенных файлов (зеленым цветом)
- Файлов с предупреждениями (желтым цветом)
- Файлов с ошибками (красным цветом)

Если в отчете есть ошибки, необходимо исправить их перед загрузкой:

- Заменить файлы на соответствующие требованиям
- Исправить метаданные в Excel-файле и загрузить его заново

### 4. Загрузка релизов

После успешной проверки файлов нажмите кнопку "Загрузить релизы". Процесс загрузки включает следующие этапы:

1. **Загрузка аудиофайлов**:

   - Файлы загружаются по протоколу TUS с поддержкой возобновления загрузки
   - Прогресс отображается для каждого файла
2. **Загрузка обложек**:

   - Изображения загружаются аналогично аудиофайлам
   - Система автоматически проверяет формат
3. **Регистрация релизов**:

   - После загрузки всех файлов система регистрирует релизы на платформе
   - Каждому релизу присваивается статус "new"
4. **Завершение загрузки**:

   - По окончании загрузки система релизы со статусом "new" будут загружены и готовы к отправке на FTP

### 5. Отправка релизов на FTP

После успешной загрузки и регистрации релизов нажмите кнопку "Отправить на FTP" для отправки релизов на модерацию:

1. Система находит все релизы со статусом "new" для текущего пользователя
2. Статус релизов изменяется на "moderation"
3. Релизы помечаются для загрузки на платформу Zvonko
4. Прогресс отправки отображается в интерфейсе

Если процесс отправки был прерван, он может быть продолжен при следующем запуске приложения.

### 6. Настройки подключения

Для настройки подключения к API платформы Gosilk:

1. Перейдите в раздел "Настройки" в боковом меню
2. Введите учетные данные:
   - ID пользователя
   - JWT токен
3. Нажмите "Сохранить"

Вы также можете сохранить несколько шаблонов токенов для разных учетных записей:

1. Введите имя шаблона
2. Введите ID пользователя и токен
3. Нажмите "Добавить шаблон"
4. Для использования шаблона выберите его из выпадающего списка

## Дополнительные функции

## Возобновление прерванной загрузки

Если загрузка была прервана, вы можете продолжить ее при следующем запуске приложения:

1. Запустите приложение
2. Система проверит наличие незавершенных загрузок
3. Если такие загрузки найдены, появится предложение продолжить их
4. Нажмите "Продолжить", чтобы возобновить загрузку с того места, где она была прервана

### Возобновление прерванной отправки на FTP

Если отправка релизов на FTP была прервана, вы можете продолжить ее при следующем запуске приложения:

1. Запустите приложение
2. Перейдите в раздел "Отправка на FTP"
3. Если есть незавершенная отправка, появится кнопка "Продолжить отправку"
4. Нажмите эту кнопку, чтобы продолжить отправку с последнего успешно обработанного релиза

## Решение проблем

### Проблемы при загрузке Excel-файла

**Проблема**: Excel-файл не загружается или данные отображаются некорректно.

**Решение**:

- Убедитесь, что файл имеет формат .xlsx или .xls
- Убедитесь, что лист с метаданными называется "Лист1"
- Проверьте, что первая строка содержит заголовки
- Убедитесь, что данные начинаются со второй строки
- Проверьте наличие специальных символов в именах файлов

### Проблемы при сопоставлении файлов

**Проблема**: Система не может сопоставить аудиофайлы или обложки с метаданными из Excel.

**Решение**:

- Убедитесь, что имена файлов в Excel точно соответствуют реальным именам файлов (включая расширения)
- Проверьте наличие пробелов, дефисов и других специальных символов
- Убедитесь, что в Excel указаны полные имена файлов (например, "Artist - Track.wav", а не просто "Track")

### Проблемы при загрузке файлов

**Проблема**: Файлы не загружаются или загрузка прерывается с ошибкой.

**Решение**:

- Проверьте подключение к интернету
- Убедитесь, что файлы соответствуют требованиям платформы
- Проверьте правильность учетных данных (ID пользователя и токен)
- Если загрузка прерывается, приложение должно автоматически возобновить ее при следующем запуске

### Проблемы при отправке на FTP

**Проблема**: Релизы не отправляются на FTP или процесс завершается с ошибкой.

**Решение**:

- Убедитесь, что релизы имеют статус "new"
- Проверьте правильность учетных данных
- Убедитесь, что все обязательные поля для релизов заполнены
- Если отправка прерывается, вы можете продолжить ее при следующем запуске приложения

Если у вас возникнут вопросы или проблемы, которые не описаны в этой документации, пожалуйста, обратитесь в службу поддержки Gosilk.
