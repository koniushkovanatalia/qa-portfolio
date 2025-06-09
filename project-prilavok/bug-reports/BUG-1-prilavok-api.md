## Результаты проверок API Прилавок 3.1.1

### **BUG-1. POST /api/v1/kits/id/products — ошибка 500 при пустом id продуктов вместо 400 Bad Request.**
 
**Приоритет:** Средний  
**Окружение:** Stage-сервер, API v3.1.1  

**Шаги для воспроизведения:**
1. Отправить POST-запрос на `/api/v1/kits/id/products`.
2. В теле запроса указать:
```json
{
  "productsList": [
    {
      "id": "",
      "quantity": 1
    }
  ]
}
```

**cURL:**
```bash
curl --location '{адрес_сервера}/api/v1/kits/11/products' \
--header 'Content-Type: application/json' \
--data '{
  "productsList": [
    {
      "id": "",
      "quantity": 1
    }
  ]
}'
```

**Ожидаемый результат:**  
Код и статус ответа 400 Bad Request.

**Фактический результат:**  
Код и статус ответа 500 Internal Server Error. HTML-страница с сообщением:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <title>Error</title>
</head>
<body>
    <pre>Internal Server Error</pre>
</body>
</html>
```
