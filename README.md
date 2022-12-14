# Контрольный проект по модулю В10

Бот конвертирует валюты.


# Порядок использования
У бота есть четыре режима работы. 
Коды валют можно вводить в верхнем и нижнем регистре.
1. Получение курса определённой валюты в рублях РФ.
Написать код валюты. Например:
```USD```
2. Конвертация определённого числа валюты в рубли РФ.
Написать число валюты и код валюты. Например:
```10 USD```
3. Конвертация одной валюты в другую.
Написать через пробел валюту, из которой будем конвертировать и код валюты, в которую будем конвертировать. 
Например, доллары США в евро:
```USD EUR```
4. Конвертировать определённое число одной валюты в другую.
Написать через пробел три значения
```
<количество первой валюты>
<имя валюты цену которой он хочет узнать> 
<имя валюты в которой надо узнать цену первой валюты> 
```

Например, 10 долларов США в евро:
```10 USD EUR```



# Команды бота:
- /start - начало работы бота
- /help - пользователю выводятся инструкции по применению бота.
- /values - должна выводиться информация о всех доступных валютах в читаемом виде.
- /usage - вывод на экран порядка использования бота

# Технологии

*Уважаемые проверяющие*, некоторые технологии были сознательно изменены для лучшей, на мой взгляд, работы бота. Например, для вычисления результата работы бота были использованы другие методы, а не статический get_price(), как было описано в задании. Считаю это допустимым улучшением кода.


1. Взятие курса валют через любое удобное API и отправлять к нему запросы библиотекой Requests.
2. Парсинг полученных ответов через библиотеку JSON.
3. Написание бота через библиотеку pyTelegramBotAPI.
4. Ошибки пользователя (например, введена неправильная или несуществующая валюта или неправильно введено число) вызывать собственно 
написанное исключение APIException с текстом пояснения ошибки.
5. Текст любой ошибки с указанием типа ошибки должен отправляться пользователю в сообщения.
6. Для отправки запросов к API описать класс со статическим методом get_price(), который принимает три аргумента: имя валюты, цену на которую надо узнать, — base, имя валюты, цену в которой надо узнать, — quote, количество переводимой валюты — amount и возвращает нужную сумму в валюте.
7. Токен telegramm-бота хранить в специальном конфиге (можно использовать .py файл).
8. Все классы спрятать в файле extensions.py.
