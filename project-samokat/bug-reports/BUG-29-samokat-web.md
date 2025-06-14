## Результаты проверок веб-приложения Самокат

### **BUG-29. При нажатии на кнопку "Заказать" экрана "Сделать заказ" появляется всплывающее окно "Хотите оформить заказ" вместо окна с номером заказа**  
**Приоритет:** Высокий
**Серьезность:** Высокая  
**Окружение:**  
- Google Chrome, ver. 132.0.6834.111 (Official Build) (arm64), 1920x1080  
- Yandex Browser, ver. 24.12.0.1845 (64-bit), 1280x720  

**Предусловия:**  
- Шаг 1: открыть веб-приложение "Самокат".  
- Шаг 2: на главной странице нажать кнопку "Заказать".  

**Шаги для воспроизведения:**  
- Шаг 1: в поле "Имя" ввести Уинстон.  
- Шаг 2: в поле "Фамилия" ввести Черчилль.  
- Шаг 3: в поле "Адрес" ввести Ходынский.  
- Шаг 4: в поле "Станция метро" выбрать Динамо.  
- Шаг 5: в поле "Номер телефона" ввести 84012000000.  
- Шаг 6: нажать на кнопку "Далее".  
- Шаг 7: в поле "Дата доставки" выбрать дату.  
- Шаг 8: в поле "Срок аренды" выбрать сутки.  
- Шаг 9: нажать кнопку "Заказать".  

**Ожидаемый результат:**  
- При нажатии на кнопку "Заказать" появляется всплывающее окно с текстом "Номер заказа NNNNN" и кнопкой "Посмотреть статус".

**Фактический результат:**  
- При нажатии на кнопку "Заказать" появляется всплывающее окно "Хотите оформить заказ?" с кнопками "Да", "Нет".
