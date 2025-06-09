## Результаты проверок API Прилавок 3.1.1

### **BUG-21. POST /fast-delivery/v3.1.1/calculate-delivery.xml — доставка "Привезем быстро" возможна при отрицательном весе продуктов в заказе.** 
  
**Приоритет:** Высокий  
**Окружение:** Stage-сервер, API v3.1.1  

**Шаги для воспроизведения:**
1. Отправить POST-запрос для доставки "Привезем быстро" `/fast-delivery/v3.1.1/calculate-delivery.xml`.
2. В теле запроса передать:

```xml
<InputModel>
    <productsCount>2</productsCount>
    <productsWeight>-5</productsWeight>
    <deliveryTime>20</deliveryTime>
</InputModel>
```

**cURL:**
```bash
curl --location '{адрес_сервера}/fast-delivery/v3.1.1/calculate-delivery.xml' \
--header 'Content-Type: application/xml' \
--data '<InputModel>
    <productsCount>2</productsCount>
    <productsWeight>-5</productsWeight>
    <deliveryTime>20</deliveryTime>
</InputModel>'
```

**Ожидаемый результат:**  
Код и статус ответа 400 Bad Request.

**Фактический результат:**  
Код и статус ответа 200 OK.

```xml
<response name="Привезём быстро" isItPossibleToDeliver="true" hostDeliveryCost="23" clientDeliveryCost="0">
    <toBeDeliveredTime>
        <min>25</min>
        <max>30</max>
    </toBeDeliveredTime>
</response>
```
