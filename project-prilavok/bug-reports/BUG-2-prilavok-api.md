## Результаты проверок API Прилавок 3.1.1

### **BUG-2. POST /api/v1/kits/id/products — сервер возвращает 200 OK вместо 400 Bad Request, если поле quantity оставить пустым ("").**

**Приоритет:** Высокий
**Окружение:** Stage-сервер, API v3.1.1

### Шаги для воспроизведения:
1. Отправить POST-запрос на добавление продуктов в набор `/api/v1/kits/id/products`
2. В теле запроса указать:
```json
{
    "productsList": [
        {
            "id": 79,
            "quantity": ""
        }
    ]
}
```

**cURL:**
```bash
curl --location '{адрес_сервера}/api/v1/kits/8/products' \
--header 'Content-Type: application/json' \
--data '{
    "productsList": [
        {
            "id": 79,
            "quantity": ""
        }
    ]
}'
```

### Ожидаемый результат:
Код и статус ответа `400 Bad Request`.

### Фактический результат:
Код и статус ответа `200 OK`.

```json
{
    "id": 8,
    "name": "В космос",
    "productsList": [
        {
            "id": 79,
            "name": "Творог «Село Зелёное» 5%",
            "price": 109,
            "weight": 200,
            "units": "г",
            "quantity": ""
        }
    ],
    "productsCount": "0"
}
```
