## Результаты проверок приложения Метро 3.6 для Android

### **BUG-3. Временной интервал маршрута не обновляется, если текущее время превышает время окончания маршрута.**

**Приоритет:** Высокий  
**Окружение:** Honor 8, Android 9.0 Pie, разрешение 1080х1920, диагональ 5.5, Метро, версия 3.6  

**Предусловия:**    
Приложение запущено.  
В настройках выбран город Москва.  

**Шаги для воспроизведения:**  
Шаг 1: Перейти на экран карты.  
Шаг 2: В поле "Откуда" ввести ЦСКА.  
Шаг 3: В поле "Куда" ввести Деловой центр.  
Шаг 4: Изменить время устройства - установить значение, превышающее конечное время маршрута на 10 минут.  

**Ожидаемый результат:**  
Временной интервал маршрута обновляется, если текущее время превышает время окончания маршрута.  

**Фактический результат:**  
Временной интервал маршрута не обновляется.
