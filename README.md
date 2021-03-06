# Blocks.json

Структура block.json

```
{
  "componentsOrder": [
    null
  ],
  "components": {
    "blockId": {
      "name": null,
      "id": null,
      "isEditing": null,
      "isInit": null
    }
  },
  "images": {
    "imageId": null
  },
  "variants": {
    "variantsId": {
      "id": null,
      "question": null,
      "answer": null,
      "points": null,
      "attempts": null,
      "comments": null,
      "hints": {
        "text": null,
        "isVisible": null
      },
      "options": [
        null
      ]
    }
  },
  "options": {
    "optionsId": {
      "id": null,
      "text": null,
      "imgId": null,
      "isValid": null,
      "checked": null
    }
  }
}
```
## Components Order

Поле ```componentsOrder``` содержит уникальные идентификаторы, которые присваиваются каждому компоненту, который был создан в редакторе.

```
"componentsOrder": ["9fa489a3-abec-4217-9542-2355fabc262b"]
```

## Components
Поле  ```components``` представляет объект, которые содержит информацию о каждом использованом компоненте. 
```
"components": {
    "9fa489a3-abec-4217-9542-2355fabc262b": {
      "name": "XMarkdown",
      "id": "9fa489a3-abec-4217-9542-2355fabc262b",
      "isVisible": true,
      "title": "",
      "isEditing": false,
      "isInit": true,
       ...
    }
    ...
```
Ключ ```9fa489a3-abec-4217-9542-2355fabc262b``` -  уникальный идентификатор компонента.
* ```name``` - "рабочее" название компонента, 
* ```id``` - уникальный идентификатор компонента, 
* ```isVisible``` - уставливает видимость компонента,
* ```title``` - устанавливает название задания.
* ```isEditing``` - указывает находится компонент в режиме редактирования, или нет.
* ```isInit``` - инициализация компонента.

Для компонентов типа **Задания**  добавляются дополнительные поля 
```
	
      "type": "task",
      "variant": "912c35a0-b775-4a49-bf6f-aeae36e6cbe3",
      "variants": [
        "912c35a0-b775-4a49-bf6f-aeae36e6cbe3"
      ]
```
* ```type``` - указывает на вид задания (Посмотреть видео и т.д),
* ```variant``` - хранит текущий уникальный ID варианта, который в данный момент выбрал пользователь.
* ```variants``` - содержит идентификаторы созданных вариантов для текущего компонента.

## Images
Поле ```images``` содержит информацию о всех картинках, которые были загружены через компоненты.
``` 
"images": {
	d68d49e2-a64a-40f9-b9a4-a05ebb5822d6.png: "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAJwAAACJCAIAAABWwcYy";
    }
```
Где ключом является ```d68d49e2-a64a-40f9-b9a4-a05ebb5822d6.png``` - уникальное имя картинки, а его значением - представление картинки закодированное в формат Base64.

## Variants
Поле ```variants``` содержит подробную информация о каждом созданном варианте.
```
"variants": {
    "912c35a0-b775-4a49-bf6f-aeae36e6cbe3": {
      "id": "912c35a0-b775-4a49-bf6f-aeae36e6cbe3",
      "question": "Вопрос",
      "answer": "ответ",
      "points": 1,
      "attempts": 1,
      "comments": "текст комментария",
      "hints": {
        "text": "текст подсказки",
        "isVisible": false
      },
      "options": [
        "4b58d713-b2c2-4c1b-b028-2efd743d3f09"
      ]
    }
  }
```
Где ```912c35a0-b775-4a49-bf6f-aeae36e6cbe3``` - уникальный ключ варианта, который связан с полем ```variants``` у ```Components```.
* ```id``` - уникальный ID варианта.
* ```questions``` - вопрос для текущего варианта.
* ```answer``` - ответ на вопрос текущего варианта, с которым сверяется ответ.
* ```points``` - количество очков, которые даются за правильный ответ.
* ```attempts``` - количество попыток, чтобы указать правильный ответ.
* ```comments``` - комментарии к заданию.
* ```hints``` - представляет информацию о подсказке и содержит в себе два поля - ```text``` - сам текст подсказки и ```isVisible```- устанавливает видимост подсказки.
* ```options``` - содержит массив уникальных ID вариантов ответа. Связан с Options.

## Options
```options``` - содержит подробную информацию о каждом варианте ответа.
```
"options": {
    "4b58d713-b2c2-4c1b-b028-2efd743d3f09": {
      "id": "4b58d713-b2c2-4c1b-b028-2efd743d3f09",
      "text": "Ответ",
      "imgId": null,
      "isValid": true
    }
  }
```
```4b58d713-b2c2-4c1b-b028-2efd743d3f09``` - уникальный ключ варианта ответа.
* ```id``` - уникальный ID варианта ответа.
* ```text``` -  текст ответа.
* ```imgId``` - ID Картинки.
* ```isValid``` - указывает правильный этот ответ или нет.

## Key Types

| Key       | Type    |
|-----------|---------|
| id        | String  |
| text      | String  |
| title     | String  |
| isEditing | Boolean |
| isValid   | Boolean |
| isVisible | Boolean |
| isInit    | Boolean |
| name      | String  |
| questions | String  |
| answer    | String  |
| point     | INT     |
| attempts  | INT     |
| comments  | String  |
