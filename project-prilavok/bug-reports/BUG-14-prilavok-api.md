## Результаты проверок API Прилавок 3.1.1

### **BUG-14. POST /api/v1/kits/id/products — сервер возвращает 200 OK вместо 400 Bad Request, если в теле запроса отсутствует id продуктов.**
 
**Приоритет:** Высокий  
**Окружение:** Stage-сервер, API v3.1.1 

**Шаги для воспроизведения:**
1. Отправить POST-запрос на добавление продуктов в набор `/api/v1/kits/id/products`.
2. В теле запроса указать:
```json
{
  "productsList": [
    {
      "quantity": 2
    }
  ]
}
```

**cURL:**
```bash
curl --location '{адрес_сервера}/api/v1/kits/21/products' \
--header 'Content-Type: application/json' \
--data '{
  "productsList": [
    {
      "quantity": 2
    }
  ]
}'
```

**Ожидаемый результат:**  
Код и статус ответа 400 Bad Request.

**Фактический результат:**  
Код и статус ответа 200 OK.  
```json
{
  "id": 21,
  "name": "В космос",
  "productsList": [
    {
      "quantity": 2
    }
  ],
  "productsCount": 2
}
```
