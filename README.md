# TA.SAMAYA-DATA

# 1. Правила формата json:

=========================================================================================================

1. {} -- определяет блок информации, к примеру курс
2. [] -- определяет набор информации (массив), к примнру медитации в курсе
3. "id": 0, -- это поле, в конце каждого поля запятая, не считая последнего
4. "text" -- все имена полей и строковые значения обязательно в двойных кавычках
5. 12345 -- числа без кавычек
6. true/false -- логические поля без кавычеи и принимают значения true или false
7. null -- отсутствие значения, если строку оставить пустоу, то будет тот же результат (строка с пробелом не пустая)

# 2. Как добавить/удалить данные:

=========================================================================================================

### !!
## ВСЕ ДАННЫЕ ДОБАВЛЯЮТСЯ И УДАЛЯЮТСЯ В СООТВЕТСТВИИ С ИЗМЕНЕНИЯМИ В ФАЙЛАХ, КУРСЫ НЕ ПРОПАДАЮТ АВТОМАТИЧЕСКИ ПО ИСТЕЧЕНИЮ СРОКА, ИХ НУЖНО УДАЛЯТЬ ВРУЧНУЮ
### !!

Данные беруться с ветки main

###### Добавить медитацию

В files/meditations.json в поле "data" размещены медитации, в приложении они отображаются по порядку и первая в списке медитация появится на главной. Для добавления новой нужно просто вставить внутри квадратных скобок медитацию, что имеет поля, соответствующие примеру.

- Если поле "accessCode" оставить пустым или присвоить null, то медитация будет доступна без кода.
- Поле "durationMeasuring" принимает только следующие значения: minutes, hours, days.
- Если поле "banner" оставить пустым или присвоить null, то вместо него будет установлено изображение по умолчанию. В противном случае оно принимает ссылку на изображение.
- Поле "lessonContent" -- это массив строк, то есть задания. Нумеровать не нужно, это делает приложение.
- Поле "media" -- это аудио или видео в зависимости от указанного типа в поле "type": "audio"/"video". в поле "uri" должен быть путь к видео/аудио.

###### Пример медитации:

    {
    "id": 1,
    "title": "Learning how to do it right",
    "description": "I had spent ...",
    "duration": 10,
    "accessCode": "1111",
    "durationMeasuring": "minutes",
    "lessonTitle": "string",
    "banner": "",
    "lessonContent": [
    "Take a seat. Find place to sit that feels calm and quiet to you.",
    "Set a time limit. ...",
    "Notice your body. ...",
    "Feel your breath. ...",
    "Notice when your mind has wandered. ...",
    "Be kind to your wandering mind. ...",
    "Close with kindness. ...",
    "Take a seat. Find place to sit that feels calm and quiet to you.",
    "Set a time limit. ...",
    "Notice your body. ...",
    "Feel your breath. ...",
    "Notice when your mind has wandered. ...",
    "Be kind to your wandering mind. ...",
    "Close with kindness. ..."
    ],
    "media": {
    "uri": "",
    "type": "audio"
    },
    "availableDays": 90,
    "startDate": null,
    "isAvailable": true
    }

###### Добавить курс

В files/practices.json в поле "data" размещены курсы, в приложении они отображаются по порядку и первый в списке курс появится на главной. Для добавления нового нужно просто вставить внутри квадратных скобок курс, что имеет поля, соответствующие примеру.

- Если поле "accessCode" оставить пустым или присвоить null, то курс будет доступна без кода.
- Поле "durationMeasuring" принимает только следующие значения: minutes, hours, days.
- Поле "content" -- это массив медитаций.

###### Пример курса:

    {
    "id": 0,
    "title": "Practice",
    "description": "It is practice",
    "duration": 2,
    "accessCode": "abc123",
    "durationMeasuring": 'days',
    "availableDays": 90,
    "startDate": 10,
    "content": [
    {
         "id": 0,
                    "title": "Day one",
                    "description": "I had spent...",
                    "duration": 10,
                    "banner": "https://nebula.org/blog/wp-content/uploads/2020/08/woman-doing-yoga-at-sunset-1024x683.jpg",
                    "accessCode": null,
                    "durationMeasuring": "minutes",
                    "lessonTitle": "string",
                    "lessonContent": [
                        "Take a seat. Find place to sit that feels calm and quiet to you.",
                        "Set a time limit. ...",
                        "Notice your body. ...",
                    ],
                    "media": {
                        "uri": "",
                        "type": "video"
                    },
                    "availableDays": 90,
                    "startDate": null,
                    "isAvailable": true
    },
    {
         "id": 1,
                    "title": "Day two",
                    "description": "I had spent...",
                    "duration": 15,
                    "banner": "https://nebula.org/blog/wp-content/uploads/2020/08/woman-doing-yoga-at-sunset-1024x683.jpg",
                    "accessCode": null,
                    "durationMeasuring": "minutes",
                    "lessonTitle": "string",
                    "lessonContent": [
                        "Take a seat. Find place to sit that feels calm and quiet to you.",
                        "Set a time limit. ...",
                        "Notice your body. ...",
                    ],
                    "media": {
                        "uri": "https://nebula.org/blog/wp-content/uploads/2020/08/woman-doing-yoga-at-sunset-1024x683.jpg",
                        "type": "audio"
                    },
                    "availableDays": 90,
                    "startDate": null,
                    "isAvailable": true
    }

]
}
