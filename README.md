# Создание и настройка базы

Источник: курс от Нетология "1С-программист: первые шаги в профессию" https://netology.ru/profile/program/onecfree-33/schedule

1. Создайте новую информационную базу и откройте ее в режиме Конфигуратор.
    
2. Установите свойства корня конфигурации:
    
    - Имя: ЛичныеФинансы
    - Синоним: Личные финансы
    - Авторские права: Ваша фамилия и имя
    - Версия: 0.0.0.1

## Создание справочников, документов и реквизитов

1. Создайте в группе Общие новый Определяемый тип ДенежнаяСумма, с типом Число (15, 2)

![2025-02-15_13-08-45](https://github.com/user-attachments/assets/99fbb374-1393-4ffc-8957-dc469d8d3af4)
    
2. Создайте перечисление **ВидыЛичныхСчетов** со значениями Наличные, Банк

![2025-02-15_13-36-25](https://github.com/user-attachments/assets/65f78f90-01ca-421a-a974-7a967234d8e7)
    
3. Создайте справочник **Валюты** с предопределенным элементом Рубль

![2025-02-15_13-40-02](https://github.com/user-attachments/assets/8bc33e73-537c-483f-86da-06ec269add1d)

4. Создайте справочник **ЛичныеСчета** с длиной наименования 150 и реквизитами:
    
    - ВидСчета - ПеречислениеСсылка.ВидыЛичныхСчетов

		![2025-02-15_13-44-08 1](https://github.com/user-attachments/assets/0c4fa053-a0f1-43cb-9f76-582fb327fa89)

    - Валюта - СправочникСсылка.Валюты

		![2025-02-15_14-03-06](https://github.com/user-attachments/assets/615b7164-6eb4-48ef-a137-d678c1dbc1a3)

5. Создайте справочник **СтатьиДвиженийДенежныхСредств** с длиной наименования 150 и включенной иерархией элементов. Создайте предопределенные элементы на верхнем уровне иерархии на свое усмотрение.

![2025-02-15_14-05-07](https://github.com/user-attachments/assets/0c22a592-6e91-4751-8e2e-02cc1279494a)
![2025-02-15_14-06-09](https://github.com/user-attachments/assets/563406f8-93dc-423f-b64e-486a3c6bd9ec)

6. Создайте справочник **Номенклатура** с длиной наименования 150 и включенной иерархией групп и элементов.

![2025-02-15_14-09-02](https://github.com/user-attachments/assets/383ad52f-3dbb-47cc-9a20-f253f2507e29)
![2025-02-15_14-09-29](https://github.com/user-attachments/assets/b3fe7d48-4dec-4f76-9c16-c6fcdd280a13)
    
7. Создайте документ **ПолучениеДохода** с реквизитами:


    - Счет - СправочникСсылка.ЛичныеСчета
    ![2025-02-15_14-12-04](https://github.com/user-attachments/assets/4fe064dd-e7bc-4b25-b9ec-fe9f2e201e5c)

    - СтатьяДохода - СправочникСсылка.СтатьиДвиженияДенежныхСредств
    ![2025-02-15_14-13-09](https://github.com/user-attachments/assets/a6d0cb6d-4512-47e4-94df-147e4f34fb72)

    - Сумма - ОпределяемыйТип.ДенежнаяСумма
    ![2025-02-15_14-15-24](https://github.com/user-attachments/assets/7a704fc0-d987-46f3-b944-d1fe425f4e50)

    - Комментарий - Строка неограниченной длины
    ![2025-02-15_14-16-16](https://github.com/user-attachments/assets/315649cb-e122-48c6-ab7f-ce06e665f2aa)


8. Создайте документ **ПереводМеждуСчетами** с реквизитами:
    
    - СчетСписания - СправочникСсылка.ЛичныеСчета
    ![2025-02-15_14-17-50](https://github.com/user-attachments/assets/d6b0d2f7-f86f-4a2d-bab4-4a37cbdbed2c)

    - СчетЗачисления - СправочникСсылка.ЛичныеСчета
    ![2025-02-15_14-18-53](https://github.com/user-attachments/assets/cedcd186-a586-4e8a-a588-bbe27b20beae)

    - Сумма - ОпределяемыйТип.ДенежнаяСумма
    ![2025-02-15_14-19-42](https://github.com/user-attachments/assets/d9c42a34-ed85-4f62-b9c4-b2427a09e184)

    - Комментарий - Строка неограниченной длины
	![2025-02-15_14-20-45](https://github.com/user-attachments/assets/6820a560-32fd-4cd8-8a29-d58cdc4ac1a8)


9. Создайте документ **Покупка** с реквизитами:
    
    - Счет - СправочникСсылка.ЛичныеСчета
    ![2025-02-15_14-21-51](https://github.com/user-attachments/assets/78ae0306-52b7-433f-901c-e5d3b3b4bb83)

    - СтатьяРасхода - СправочникСсылка.СтатьиДвиженияДенежныхСредств
    ![2025-02-15_14-22-46](https://github.com/user-attachments/assets/75cab8bd-2ec7-4736-bb6d-4b44fe1c234d)

    - РазделитьПоТоварам - Булево
    ![2025-02-15_14-23-25](https://github.com/user-attachments/assets/f729c7a9-6880-4ac5-b4f8-1b0e21c60754)

    - Сумма - ОпределяемыйТип.ДенежнаяСумма
    ![2025-02-15_14-24-11](https://github.com/user-attachments/assets/f7d1b6b4-085d-4bec-8f90-035c64d38c3e)

    - Комментарий - Строка неограниченной длины
    ![2025-02-15_14-24-54](https://github.com/user-attachments/assets/b5e9050b-4aaa-405e-a029-ac9aa7ee64eb)

    - Табличной частью ТоварыУслуги с колонками:
        - Номенклатура - СправочникСсылка.Номенклатура
        ![2025-02-15_14-26-37](https://github.com/user-attachments/assets/b8c22411-87e0-41d5-8463-6b69c2e53a03)

        - Количество - Число (10, 0)
        ![2025-02-15_14-27-49](https://github.com/user-attachments/assets/b7681cad-98fd-4941-b828-d4a28ac7edb7)

        - Цена - ОпределяемыйТип.ДенежнаяСумма
        ![2025-02-15_14-28-35](https://github.com/user-attachments/assets/7cf6bfb8-b3f0-4770-ba07-2b1d4de32f4d)

        - Сумма - ОпределяемыйТип.ДенежнаяСумма
        ![2025-02-15_14-29-24](https://github.com/user-attachments/assets/ee1eeb0c-83f6-48b2-b36c-13ebdcf732ef)


## Настройка интерфейса

1. В группе Общие создайте подсистемы:
    
    - Финансы, с составом:
        - Документ ПолучениеДохода
        - Документ ПереводМеждуСчетами
        - Документ Покупка
        ![2025-02-15_14-30-46](https://github.com/user-attachments/assets/c613d84e-93eb-4df8-9495-69cc513b4c1f)

    - Настройки, с составом:
        - Справочник Валюты
        - Справочник ЛичныеСчета
        - Справочник СтатьиДвиженийДенежныхСредств
        - Справочник Номенклатура
        ![2025-02-15_14-31-24](https://github.com/user-attachments/assets/39d5dec1-8df2-47ab-83d1-6fd1109f3d6d)

2. В корне конфигурации откройте свойство Интерфейс клиентского приложения, разместите панели так, как на ваш взгляд оптимальнее для работы с приложением. Можно запустить приложение, посмотреть получившийся результат и перенастроить.

	![2025-02-15_14-32-48](https://github.com/user-attachments/assets/07b456d5-91b9-4c61-8f20-b57818d815b1)
	
    
3. В группе Общие создайте новый стиль, настройте для стиля цветовое оформление приложения на свой вкус. В корне конфигурации установите новый стиль в свойстве Основной стиль.
    ![2025-02-15_14-53-16](https://github.com/user-attachments/assets/e34f9a8b-9b57-403d-b9d3-b8ed448ea0a5)


## Создание и настройка формы документа

1. Создайте форму документа для документа Покупка

![2025-02-18_12-25-51](https://github.com/user-attachments/assets/3b6ffe36-a300-401b-8b05-2877da3ed829)

    
2. Реализуйте в форме документа процедуру для управления видимостью элементов УправлениеВидимостьюЭлементовФормы с директивой компиляции &НаКлиентеНаСервереБезКонтекста.

Примерный код процедуры

```bsl
&НаКлиентеНаСервереБезКонтекста
Процедура УправлениеВидимостьюЭлементовФормы(Форма)
	
	Элементы = Форма.Элементы;
	Объект = Форма.Объект;
	
	РазделитьПоТоварам = Объект.РазделитьПоТоварам;
	
	Элементы.ТоварыУслуги.Видимость = РазделитьПоТоварам;
	Элементы.Сумма.ТолькоПросмотр = РазделитьПоТоварам;
	
КонецПроцедуры
```

![2025-02-18_12-27-47](https://github.com/user-attachments/assets/3ec87cf7-d7e3-4893-bcf6-9f9b035a03cd)


3. Для формы назначьте обработчик события ПриСозданииНаСервере. В обработчике вызовите ранее созданную процедуру `УправлениеВидимостьюЭлементовФормы(ЭтотОбъект);`

![2025-02-18_12-30-32](https://github.com/user-attachments/assets/1ccd5cbf-aa43-4e5e-91c3-5b9e3d3af5d2)


```bsl
&НаСервере
Процедура ПриСозданииНаСервере(Отказ, СтандартнаяОбработка)
	УправлениеВидимостьюЭлементовФормы(ЭтотОбъект);
КонецПроцедуры
```

4. Для элемента **РазделитьПоТоварам** назначте обработчик события ПриИзменении. В обработчике вызовите ранее созданную процедуру `УправлениеВидимостьюЭлементовФормы(ЭтотОбъект);`

- зайти в раздел "Форма"
- правой клавишей по "РазделитьПоТоварам" 
- "События"
- выбрать <ПриИзменении>
- нажать "ОК"
- в разделе "Модуль" отобразится часть кода
- к нему добавить строку "`УправлениеВидимостьюЭлементовФормы(ЭтотОбъект);`"

```bsl
&НаКлиенте
Процедура РазделитьПоТоварамПриИзменении(Элемент)
	УправлениеВидимостьюЭлементовФормы(ЭтотОбъект);
КонецПроцедуры
```

![2025-02-18_13-00-44](https://github.com/user-attachments/assets/25970f10-3256-4ada-87b3-176f450852be)

    
5. Реализуйте в документе процедуру для расчета суммы документа РассчитатьИтогДокумента с директивой компиляции &НаКлиенте.

Примерный код процедуры

```bsl
&НаКлиенте
Процедура РассчитатьИтогДокумента()
	
	Объект.Сумма = Объект.ТоварыУслуги.Итог("Сумма");
	
КонецПроцедуры
```

6. Реализуйте в документе процедуру для расчета стоимость в строке табличной части и последующего пересчета суммы документа РассчитатьСуммуСтроки с директивой компиляции &НаКлиенте.

Примерный код процедуры
```bsl
&НаКлиенте
Процедура РассчитатьСуммуСтроки(Строка)
	
	Строка.Сумма = Строка.Цена * Строка.Количество;
	
	РассчитатьИтогДокумента();
	
КонецПроцедуры
```

7. Для элементов НоменклатураКоличество и НоменклатураЦена назначте обработчики события ПриИзменении. В обработчике вызовите ранее созданную процедуру с передачей текущей строки:

```bsl
&НаКлиенте
Процедура НоменклатураКоличествоПриИзменении(Элемент)
	ТекущиеДанные = Элементы.ТоварыУслуги.ТекущиеДанные;
	РассчитатьСуммуСтроки(ТекущиеДанные);
КонецПроцедуры

&НаКлиенте
Процедура НоменклатураЦенаПриИзменении(Элемент)
	ТекущиеДанные = Элементы.ТоварыУслуги.ТекущиеДанные;
	РассчитатьСуммуСтроки(ТекущиеДанные);
КонецПроцедуры

```
# Итог всего кода "Модуль" документа "Покупка":

```bsl
&НаКлиентеНаСервереБезКонтекста
Процедура УправлениеВидимостьюЭлементовФормы(Форма)
	
	Элементы = Форма.Элементы;
	Объект = Форма.Объект;
	
	РазделитьПоТоварам = Объект.РазделитьПоТоварам;
	
	Элементы.ТоварыУслуги.Видимость = РазделитьПоТоварам;
	Элементы.Сумма.ТолькоПросмотр = РазделитьПоТоварам;
	
КонецПроцедуры

&НаСервере
Процедура ПриСозданииНаСервере(Отказ, СтандартнаяОбработка)
	УправлениеВидимостьюЭлементовФормы(ЭтотОбъект);
КонецПроцедуры

&НаКлиенте
Процедура РазделитьПоТоварамПриИзменении(Элемент)
	УправлениеВидимостьюЭлементовФормы(ЭтотОбъект);
КонецПроцедуры

&НаКлиенте
Процедура РассчитатьИтогДокумента()
	
	Объект.Сумма = Объект.ТоварыУслуги.Итог("Сумма");
	
КонецПроцедуры

&НаКлиенте
Процедура РассчитатьСуммуСтроки(Строка)
	
	Строка.Сумма = Строка.Цена * Строка.Количество;
	
	РассчитатьИтогДокумента();
	
КонецПроцедуры  

&НаКлиенте
Процедура НоменклатураКоличествоПриИзменении(Элемент)
	ТекущиеДанные = Элементы.ТоварыУслуги.ТекущиеДанные;
	РассчитатьСуммуСтроки(ТекущиеДанные);
КонецПроцедуры

&НаКлиенте
Процедура НоменклатураЦенаПриИзменении(Элемент)
	ТекущиеДанные = Элементы.ТоварыУслуги.ТекущиеДанные;
	РассчитатьСуммуСтроки(ТекущиеДанные);
КонецПроцедуры

```
## Создание регистра сведений для хранения курсов валют

1. Создайте регистр сведений **КурсыВалют**. Периодичность - День.

![2025-02-18_13-15-37](https://github.com/user-attachments/assets/2b89c539-bc20-404c-82d4-75b287b20c46)

- "Регистры сведений" -- правой кнопкой -- "Добавить" -- в поле "Имя" ввести "КурсыВалют" -- кнопка "Tab"
- в поле "Периодичность" выбираем "В пределах дня"

![2025-02-18_13-18-52](https://github.com/user-attachments/assets/ddecbbcd-d914-482c-bd42-ef0a3f88ce38)

 
- вкладка "Данные"
	- выделить "Измерения" -- нажать на зеленый плюс "Добавить" 
		- в поле "Имя" ввести "Валюта"
		- в поле "Тип" выбрать "СправочникСсылка.Валюты"

	![2025-02-18_13-21-45](https://github.com/user-attachments/assets/ceea8f0d-d98b-40e6-af64-0c468c798138)


	- выделить "Ресурсы" -- нажать на зеленый плюс "Добавить" 
		- в поле "Имя" ввести "Кратность"
		- в поле "Тип" выбрать "Число"

	![2025-02-18_13-27-37](https://github.com/user-attachments/assets/7d4b6464-5bfe-4cc5-9cb8-aeb9d8aaf4e2)


	 - выделить "Ресурсы" -- нажать на зеленый плюс "Добавить" 
		- в поле "Имя" ввести "Курс"
		- в поле "Тип" выбрать "Число"
		- в поле "Длина" ввести "15"
		- в поле "Точность ввести "4"
    
	![2025-02-18_13-29-33](https://github.com/user-attachments/assets/a5badd5e-4e02-4588-9730-97027cba775d)


2. Включите регистр сведений в одну из созданных подсистем
- вкладка "Подсистемы" -- поставить галочку в любой подсистеме

    ![2025-02-18_13-20-32](https://github.com/user-attachments/assets/699c3b48-4b64-4080-96c6-b9f4e91b9ef5)


## Загрузка курсов валют

1. Создайте обработку **ЗагрузкаКурсаВалюты**

	- правой кнопкой по "Обработки"
	- нажать "Добавить"
	- в поле "Имя" ввести "ЗагрузкаКурсаВалюты"
	- нажать кнопку "Tab"
	![2025-02-18_13-33-37](https://github.com/user-attachments/assets/291efc7c-a0d1-4ea3-8a0e-4511818fcebd)


2. Включите обработку в одну из созданных подсистем

	- вкладка "Подсистемы"
	- поставить галочку "Финансы"
	![2025-02-18_13-34-04](https://github.com/user-attachments/assets/ab09963d-d53e-4481-8f1d-0f27fad17b7e)


3. Создайте форму обработки

	- раскрыть список "ЗагрузкаКурсаВалюты"
	- правой кнопкой по "Формы"
	- нажать "Добавить"
	![2025-02-18_13-35-24](https://github.com/user-attachments/assets/9ffda0b5-7fe0-4a3a-bd6e-46190820fbce)

	- кнопка "Готово"
	![2025-02-18_13-36-34](https://github.com/user-attachments/assets/6ca88dc2-e3a2-4c23-b8fe-3c1484a269d7)


4. Создайте команду на форме обработки, вынесите на командную панель, назначьте кнопкой по умолчанию, создайте обработчик на клиенте и на сервере

	- Во вкладке "Команда формы" нажать зеленый плюс "Добавить"
	![2025-02-18_13-38-55](https://github.com/user-attachments/assets/a957173f-7923-4b1e-8a7d-255613552020)

	- перетащить "Кнопка1" в окно с формой в "Командная панель"
	![2025-02-18_13-57-59](https://github.com/user-attachments/assets/074d7516-7ab1-4f67-9246-bbef28b67780)

	- дважды щелкнуть по "ФормаКоманда1"
	- в чек-боксе "КнопкаПоУмолчанию" -- поставить галочку
	![2025-02-18_13-58-55](https://github.com/user-attachments/assets/c9810d02-954b-49d6-a8df-ca1f3bfcfa92)

	- правой кнопкой по "ФормаКоманда1" -- нажать <Действия команды>
	![2025-02-18_14-01-46](https://github.com/user-attachments/assets/9765f5dc-c77f-4203-a699-5f75e3a839ee)

	- выбрать "Создать на клиенте и процедуру на сервере" -- нажать кнопку "ОК"
	![2025-02-18_14-04-48](https://github.com/user-attachments/assets/aecc27ef-a6fe-404b-99bd-4ec18e8a0461)

	- результат в "Модуль"
	```bsl
	&НаКлиенте
	Процедура Команда1(Команда)
		Команда1НаСервере();
	КонецПроцедуры
	
	&НаСервере
	Процедура Команда1НаСервере()
		// Вставить содержимое обработчика.
	КонецПроцедуры
	```

5. В процедуру на клиенте после вызова сервера добавьте строчку для оповещения пользователя об успешной загрузке `ПоказатьОповещениеПользователя("Курсы валют загружены");`

	```bsl
	&НаКлиенте
	Процедура Команда1(Команда)
		Команда1НаСервере();
		ПоказатьОповещениеПользователя("Курсы валют загружены");
	КонецПроцедуры
	```

6. В процедуру на сервере добавьте последовательный вызов процедур по получению данных с сайта и записи полученных данных в базу:
    
	```bsl
	&НаСервере
	Процедура Команда1НаСервере()
		ДанныеСайта = ПолучитьДанныеССайта();
		ЗаписатьКурсыВалют(ДанныеСайта);
	КонецПроцедуры
	```

7. Реализуйте алгоритм процедуры по получению данных с сайта и записи полученных данных в базу:

	Пример кода для решения задачи
	```bsl
	&НаСервере
	Функция ПолучитьДанныеССайта()
		
		Соединение = Новый HTTPСоединение("www.cbr-xml-daily.ru", 443,,,,, Новый ЗащищенноеСоединениеOpenSSL);
		
		Запрос = Новый HTTPЗапрос("/daily_utf8.xml");
		
		Ответ = Соединение.Получить(Запрос);
		
		Если Ответ.КодСостояния <> 200 Тогда
			ВызватьИсключение "Ошибка соединения с сайтом ЦБ";
		КонецЕсли;
		
		Возврат Ответ.ПолучитьТелоКакСтроку();
		
	КонецФункции
	
	&НаСервере
	Процедура ЗаписатьКурсыВалют(ДанныеСайта)
		
		Чтение = Новый ЧтениеXML;
		Чтение.УстановитьСтроку(ДанныеСайта);
		
		Построитель = Новый ПостроительDOM;
		Документ = Построитель.Прочитать(Чтение);
		
		Для Каждого Узел Из Документ.ЭлементДокумента.ДочерниеУзлы Цикл
			
			Кратность = 1;
			Курс = 1;
			СимвольныйКод = "";
			
			Для Каждого СвойствоВалюты Из Узел.ДочерниеУзлы Цикл
				Если СвойствоВалюты.ИмяУзла = "CharCode" Тогда
					СимвольныйКод = СвойствоВалюты.ТекстовоеСодержимое;
				КонецЕсли;
				Если СвойствоВалюты.ИмяУзла = "Nominal" Тогда
					Кратность = Число(СвойствоВалюты.ТекстовоеСодержимое);
				КонецЕсли;
				Если СвойствоВалюты.ИмяУзла = "Value" Тогда
					Курс = Число(СвойствоВалюты.ТекстовоеСодержимое);
				КонецЕсли;
			КонецЦикла;
			
			Валюта = Справочники.Валюты.НайтиПоКоду(СимвольныйКод);
			
			Если Не ЗначениеЗаполнено(Валюта) Тогда
				Продолжить;
			КонецЕсли;		
			
			Запись = РегистрыСведений.КурсыВалют.СоздатьМенеджерЗаписи();
			Запись.Период = ТекущаяДата();
			Запись.Валюта = Валюта;
			Запись.Кратность = Кратность;
			Запись.Курс = Курс;
			Запись.Записать();
			
		КонецЦикла;	
		
	КонецПроцедуры
	```
 
## Использование накопленных данных. Отчёты и дашборды

### Процесс выполнения

Перед началом выполнения задания желательно добавить 5-10 документов каждого вида и загрузить курсы валют, чтобы отчеты в финальной части задания содержали достаточное количество данных.

### Реализация метода для перевода сумм из рублей в валюту и обратно


1. Реализуйте экспортные методы СуммаВВалюте и СуммаВРублях в модуле менеджера регистра сведений КурсыВалют

- раскрыть список "Регистры сведений" -- правой кнопкой по ранее созданному "КурсыВалют" -- "Открыть модуль набора записей" -- добавить код:

```bsl
Функция СуммаВВалюте(Сумма, Валюта, Период = Неопределено) Экспорт
	
	Если Валюта = Справочники.Валюты.РоссийскийРубль Тогда
		Возврат Сумма;
	КонецЕсли;	
	
	Запрос = Новый Запрос;
	Запрос.Текст = "ВЫБРАТЬ
	               |	КурсыВалютСрезПоследних.Кратность КАК Кратность,
	               |	КурсыВалютСрезПоследних.Курс КАК Курс
	               |ИЗ
	               |	РегистрСведений.КурсыВалют.СрезПоследних(&Период, Валюта = &Валюта) КАК КурсыВалютСрезПоследних";
	
	Запрос.УстановитьПараметр("Период", Период);
	Запрос.УстановитьПараметр("Валюта", Валюта);
	
	РезультатЗапроса = Запрос.Выполнить();
	
	Если РезультатЗапроса.Пустой() Тогда
		ШаблонСообщения = "Курс валюты %1 не установлен";
		ВызватьИсключение СтрШаблон(ШаблонСообщения, Валюта);
	КонецЕсли;
	
	Выборка = РезультатЗапроса.Выбрать();
	Выборка.Следующий();
	
	Возврат Сумма * Выборка.Кратность / Выборка.Курс;	
	
КонецФункции

Функция СуммаВРублях(Сумма, Валюта, Период = Неопределено) Экспорт
	
	Если Валюта = Справочники.Валюты.РоссийскийРубль Тогда
		Возврат Сумма;
	КонецЕсли;	
	
	Запрос = Новый Запрос;
	Запрос.Текст = "ВЫБРАТЬ
	               |	КурсыВалютСрезПоследних.Кратность КАК Кратность,
	               |	КурсыВалютСрезПоследних.Курс КАК Курс
	               |ИЗ
	               |	РегистрСведений.КурсыВалют.СрезПоследних(&Период, Валюта = &Валюта) КАК КурсыВалютСрезПоследних";
	
	Запрос.УстановитьПараметр("Период", Период);
	Запрос.УстановитьПараметр("Валюта", Валюта);
	
	РезультатЗапроса = Запрос.Выполнить();
	
	Если РезультатЗапроса.Пустой() Тогда
		ШаблонСообщения = "Курс валюты %1 не установлен";
		ВызватьИсключение СтрШаблон(ШаблонСообщения, Валюта);
	КонецЕсли;
	
	Выборка = РезультатЗапроса.Выбрать();
	Выборка.Следующий();
	
	Возврат Сумма * Выборка.Курс / Выборка.Кратность;	
	
	
КонецФункции
```

![2025-03-06_12-14-54](https://github.com/user-attachments/assets/793bf541-9c78-4010-932a-f055fdd0ff8a)


### Создание регистров накопления


1. Создайте регистр накопления ЛичныеСчета с видом Остатки. Регистраторы: ПолучениеДохода, Покупка, ПереводМеждуСчетами

![2025-03-06_12-16-32](https://github.com/user-attachments/assets/be63cbaf-12ea-4a3a-b142-bda9e02bc2b5)

![2025-03-06_12-20-44](https://github.com/user-attachments/assets/375bdf37-7df1-4526-a5c7-6703920ad3dc)

- Измерение Счет - СправочникСсылка.ЛичныеСчета

  ![2025-03-06_12-21-59](https://github.com/user-attachments/assets/836e709c-c383-42cd-b144-d5cb4f370afe)

- Измерение Валюта - СправочникСсылка.Валюты

![2025-03-06_12-22-53](https://github.com/user-attachments/assets/88722e81-027d-4357-91aa-c8c862c1ad6e)

    
- Ресурс Сумма - Число (15, 2)
  
![2025-03-06_12-23-54](https://github.com/user-attachments/assets/cd879de6-e604-48f1-a772-11405ea28bc0)

- Ресурс СуммаВал - Число (15, 2)

![2025-03-06_12-24-54](https://github.com/user-attachments/assets/caaf8df5-789d-40fa-b6b5-0a38b769eb5c)

2. Создайте регистр накопления Доходы с видом Обороты. Регистраторы: ПолучениеДохода

![2025-03-06_12-25-55](https://github.com/user-attachments/assets/6c2376e4-4d32-43bf-a632-1ae26e232954)

![2025-03-06_12-26-36](https://github.com/user-attachments/assets/17491f33-45de-42e1-9f23-06dc9a6bc813)

- Измерение СтатьяДохода - СправочникСсылка.СтатьиДвиженийДенежныхСредств

![2025-03-06_12-27-31](https://github.com/user-attachments/assets/1a04c782-82a7-4c92-9394-4af018f55163)

- Измерение Валюта - СправочникСсылка.Валюты

![2025-03-06_12-28-18](https://github.com/user-attachments/assets/e7341693-68ba-4fb0-b00e-125b8e112e61)

- Ресурс Сумма - Число (15, 2)

![2025-03-06_12-29-04](https://github.com/user-attachments/assets/96ed94d1-f88e-48bc-9297-04250d16907b)

- Ресурс СуммаВал - Число (15, 2)

![2025-03-06_12-29-50](https://github.com/user-attachments/assets/a142724d-263e-4195-be07-299bec5c9d06)


3. Создайте регистр накопления Расходы с видом Оброты. Регистраторы: ПолучениеДохода

![2025-03-06_12-30-48](https://github.com/user-attachments/assets/22f614d4-f939-4199-b870-455ced82050c)

![2025-03-06_12-31-28](https://github.com/user-attachments/assets/d4208be8-1b71-42ba-b022-bc6c625d7423)

- Измерение СтатьяДохода - СправочникСсылка.СтатьиДвиженийДенежныхСредств

![2025-03-06_12-32-11](https://github.com/user-attachments/assets/ec032cba-b2ce-4015-960b-d7d9a5321f57)
  
- Измерение Номенклатура - СправочникСсылка.Номенклатура

![2025-03-06_12-33-12](https://github.com/user-attachments/assets/5b2b36ee-47ba-4762-b096-bb7f75ee3e24)

- Измерение Валюта - СправочникСсылка.Валюты

![2025-03-06_12-33-57](https://github.com/user-attachments/assets/af81b7f9-75fb-4cad-8f60-d92dd3531a6d)

- Ресурс Сумма - Число (15, 2)

![2025-03-06_12-34-39](https://github.com/user-attachments/assets/0d5d230e-edf4-43b5-aa2a-ef580df951ed)

- Ресурс СуммаВал - Число (15, 2)

![2025-03-06_12-35-20](https://github.com/user-attachments/assets/a4919d32-3108-496c-87da-a8a4cb3050c4)


### Формирование движений


1. Для документа ПолучениеДохода с помощью конструктора движений создайте алгоритм формирования движения по регистрам ЛичныеСчета и Доходы
	
![2025-03-06_15-32-20](https://github.com/user-attachments/assets/ad24a51e-d0be-4724-80be-cbfe7a525008)

![2025-03-06_15-29-37](https://github.com/user-attachments/assets/5437b3f7-7fe7-441e-b34d-f2aec6290d9c)

![2025-03-06_15-29-53](https://github.com/user-attachments/assets/df5c35a2-d453-4512-84f7-38fd69946296)

![2025-03-06_15-30-21](https://github.com/user-attachments/assets/d80c0a42-ddfa-4f15-9796-2b6f619e1f7c)

    
2. Для документа Покупка с помощью конструктора движений создайте алгоритм формирования движения по регистрам ЛичныеСчета и Расходы

![2025-03-06_15-35-21](https://github.com/user-attachments/assets/f4d24a63-1271-4eed-8c4e-2d260540898f)

![2025-03-06_15-36-20](https://github.com/user-attachments/assets/2922f657-a14c-453c-9cd8-9f0e2188abba)

![2025-03-06_15-37-12](https://github.com/user-attachments/assets/d2d6c577-4aa7-4474-a0c8-553b8bc1491b)
   
3. Для документа ПереводМеждуСчетами с помощью конструктора движений создайте алгоритм формирования движения по регистру ЛичныеСчета

![2025-03-06_15-38-32](https://github.com/user-attachments/assets/89f2c83a-9fc9-44fd-9ec3-bea4380062f7)

4. Во всех документах для заполнения ресурсов Сумма и СуммаВал используйте методы СуммаВВалюте и СуммаВРублях из модуля менеджера регистра **КурсыВалют**



















