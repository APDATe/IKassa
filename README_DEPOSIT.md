# IKassa
Внешняя компонента работы с кассовыми аппаратами 3в1

# Методы работы в 1С Предприятие 7.7

### Метод  Внесение()

Данный метод выполняет внесеня указанной суммы в кассу и принимает следующие параметры

Параметр | Описание
---|---
ИмяКассира | Имя кассира (Хотя бы 1 символ. Все что больше 16 символов, отбрасывается).
Сумма | тип Число два знача после запятой (разделитель любой! - (Точка либо запятая не Важно!).

### Метод  Внесение().Закрыть("http://192.168.111.212:37015/v1", "75928")
Данный метод закрывает документ и принимает параметры непосредственно в методе 

Параметр | Описание
---|---
URL:PORT | URL - адрес кассового аппарта с портом (должен всегда заканчиваться /v1 
Пин-код |  пароль кассира (указан в паспорте токена)

### Представление синтаксиса 1С Предприятие 7.7

```1C
//Подключаем компоненту
МояКасса = СоздатьОбъект("AddIn.V7AlexEngineKassa");
//Создаем новый экземпляр класса Внесение();	
Документ =  МояКасса.Внесение();
//Заполняем параметры класса Внесение();
Документ.ИмяКассира  = "Иванова";
Документ.Сумма = 100.50;

//Выполняем метод Закрыть(string "URL", string "PinKod") класса Внесение();
ответ = Документ.Закрыть("http://192.168.111.212:37015/v1", "75928");

```

### Метод Закрыть() любого класса возвращает следующие параметры

Параметр | Описание
---|---
КодОтвета | Коды ответа тип-число * [Описание кодов ошибок](./resultCode.md)
Детали |  Описание кода ответа 

* [Описание метода ОткрытьСмену()](./README_OPEN_SHIFT.md)
* [Описание метода ПРОДАЖА()](./README_SALE.md)
