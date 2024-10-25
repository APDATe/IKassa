# Внешняя компонента для 1С: Предприятие 7.7

Данная компонента является неким транспортом, упрощающим механизм работы с кассами 3 в 1 компании ImLab
многие механизмы стандартной взаимосвязи между стандартным протоколом Учетной системы => Касса упрощены 
для легкого внедрения кассового оборудования в предприятие, для учета которых является учетная система на базе 
1С: Предприятие 7.7.

Например, такие методы как авторизация, прочая нформация, не учтены для 1С за ненадобностью. 
Все, что требуется из 1С (Синтаксисом) 1С передать URL  и  Пин-код кассы.

Общий принцип взаимодествия нацелен на синтаксис 1С 7.7 и представляет собой что-то подобное:

* Сперва необхоидмо подключеть внешнюю компоненту, делается это так:
```
МояКасса = СоздатьОбъект("AddIn.V7AlexEngineKassa");
```
* далее необходимо создать новый класс для работы, список классов и его методы описаны ниже!
* Пусть это будет печать X-Отчета
```
Документ = МояКасса.ПечатьХОтчета();
```
* Далее необходимо передать параметры (если они имеются), делается это примерно так - 'Документ.Параметры'
```
Документ.ПечататьЧек = 1;
```
* После передачи всех необходимых парамтеров закрываем чек методом Закрыть()
```
Ответ = Документ.Закрыть("http://192.168.111.212:37015/v1", "12345");
```
#### При этом компонента вернет Вам ответ вида

Параметр | Описание
---|---
КодОтвета | Коды ответа тип-число далее здесь приложу ссылку на описание кодов ответа 
Детали |  Описание кода ответа


# Основные методы компоненты

* [Описание метода СостояниеКассы()](./README_OTHER_INFO.md)
* [Описание метода ОткрытьСмену()](./README_OPEN_SHIFT.md)
* [Описание метода Внесение()](./README_DEPOSIT.md)
* [Описание метода ПРОДАЖА()](./README_SALE.md)
* [Описание метода АннулированиеЧека()](./README_ROLLBACK_CHECK.md)
* [Описание метода Возврат()](./README_MoneyBack.md)
* [Описание метода ПечатьХОтчета()](./README_X_REPORT.md)
* [Описание метода ПечатьДокумента()](./README_PRINT.md)
* [Описание метода Изъятие()](./README_WITHDRAW.md)
* [Описание метода ЗакрытиеСмены()](./README_CLOSE_SHIFT.md)
* [Описание метода ПечатьПоследнегоОтчетаЗакрытияСмены()](./README_PRINT_Z_REPORT.md)
