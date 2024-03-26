# Hezzl-QA-task
Postman, SQL, test cases
>тз https://docs.google.com/document/d/1jhegfPcimR3HQHeqiGzDlKKEQtD0tZWOX6_TJn-KwUc/edit?clckid=c73d15e1

**Задание 1. В POSTMAN созданы 2 коллекции, для запуска в POSTMAN нужно скачать и запустить файлы "Hezzlmania INIT.postman_collection.json", "Hezzlmania INIT.postman_collection.json"**  
КОЛЛЕКЦИЯ INIT  
Метод Init  
КОЛЛЕКЦИЯ LOGIN  
Метод CheckLogin  
Метод ConfirmCode  

**Задание 2. SQL запрос в базу, который бы достал все записи с учетом фильтров:**  
campaignId = 145602  
31 декабря 2023 <=  date < 31 января 2024  
>SELECT *  
>FROM имя_таблицы  
>WHERE campaignId = 145602  
>AND date >= '2023-12-31 00:00:00'  
>AND date < '2024-01-31 00:00:00';  


**Задание 3. 10 тест-кейсов на бросок кубика в игре https://play.hezzl.com в первом лабиринте**

браузер:	Chrome Version 116.0.5845.187  
Предусловие: игра "лабиринт сокровищ" запущена: в меню игр под игрой "лабиринт сокровищ" кликнута кнопка "играть", далее на странице игры выбрана кнопка "начать")
| ID | Тест-кейс                                                                     | Шаги для воспроизведения                                                                     | Ожидаемый результат                                                                                   | Фактический результат                                                                                   |
|----|--------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
| 1  | Проверить, что корректно отображается игровое поле с кубиком при броске кубика | 1. Выполнить предусловие. <br> 2. Кликнуть по кнопке броска кубика "пуск". <br> 3. Проверить, что игровое поле отображается корректно, не лагает, происходит звуковое сопровождение. <br> 4. Проверить, что отрабатывает анимация кубика. | Игровое поле отображается корректно, не лагает, происходит звуковое сопровождение. Отрабатывает анимация кубика. | Игровое поле отображается корректно, не лагает, происходит звуковое сопровождение. Отрабатывает анимация кубика. |
| 2  | Проверить, что при броске кубика выпадает случайное число от 1 до 6            | 1. Выполнить предусловие. <br> 2. Кликнуть по кнопке броска кубика "пуск". <br> 3. Проверить, что выпавшее число находится в диапазоне от 1 до 6.               | Выпадает кубик с числом 3, лежит в диапазоне 1-6.                                                        | Случайное число от 1 до 6                                                                                |
| 3  | Проверить, что персонаж передвигается на количество шагов, равное выпавшему числу на кубике | 1. Выполнить предусловие. <br> 2. Проверить начальную позицию персонажа. <br> 3. Кликнуть по кнопке броска кубика "пуск" и получить значение кубика. <br> 4. Проверить, что персонаж переместился на количество шагов, равное выпавшему числу. | Выпадает число 6, персонаж переместился на 6 шагов.                                                    | Персонаж переместился на количество шагов, равное выпавшему числу.                                       |
| 4  | Проверить, что числа на кубике выпадают случайным образом                      | 1. Выполнить предусловие. <br> 2. Бросать кубик 10 раз, выпавшие числа: 2, 3, 5, 2, 6, 1, 4, 2, 5, 2. <br> 3. Проверить, что каждое число выпадает примерно одинаковое количество раз (с учетом статистической погрешности), случайным образом. | Выпадают поочередно цифры: 2, 3, 5, 2, 6, 1, 4, 2, 5, 2.                                                    | Каждое число выпадает примерно одинаковое количество раз (с учетом статистической погрешности), случайным образом |
| 5  | Проверка работы игры при различных разрешениях экрана                          | 1. Выполнить предусловие на различных разрешениях экрана (мобильный телефон, ноутбук, настольный компьютер). <br> 2. Проверить, что игровое поле, кнопки и другие элементы интерфейса отображаются корректно. <br> 3. Протестировать основную функциональность игры(бросить кубик 10 раз, применить помогайки, зайти и выйти из игры в течение сеанса). | Игра корректно отображается и функционирует на разрешениях: <br> 800x600, <br> 1280x720, <br> 1366x768 <br> 1536x864, <br> 1920x1080, <br> 2560x1080, <br> мобильной версии: <br> 360x800, <br> 393x851, <br> 414x896 | Игра корректно отображается и функционирует на разрешениях экрана: <br> 800x600 <br> 1280x720 <br> 1366x768 <br> 1536x864, <br> 1920x1080, <br> 2560x1080, <br> мобильной версии: <br> 360x800, <br> 393x851, <br> 414x896 |
| 6  | Проверка работы игры на различных операционных системах                       | 1. Выполнить предусловие на macOS и на iOS(поочередно). <br> 2. Проверить, что игра запускается и отображается без ошибок. <br> 3. Протестировать основную функциональность игры на каждой операционной системе(бросить кубик 10 раз, применить помогайки, зайти и выйти из игры в течение сеанса). | Игра корректно отображается и функционирует на macOS, iOS | Игра корректно отображается и функционирует на macOS, iOS |
| 7  | Проверка отработки элемента награды/приза/ячейки-действия на клетке поля, куда приходит персонаж               | 1. Выполнить предусловие. <br> 2. Бросить кубик 2 раза (выпавшие значения 2 и 6) и передвигаться на 2 и 6 клеток соответственно.                    | результат первого броска кубика - 2, перемещение персонажа на 2ую клетку вперед, получение нагады. результат второго броска кубика - 6, перемещение персонажа на 6ую клетку вперед, активация ячейки-действия 6ой клетки.            | Полное отрабатывания элемента награды/приза/ячейки-действия на клетке поля, куда приходит персонаж.          |
| 8  | Проверка работы бонуса "Плюс один кубик на 2 хода"                                                                | 1. Выполнить предусловие. <br> 2. Кликнуть на элемент "помогайки" справа, перейти в меню бонусов. <br> 3. Кликнуть по бонус "Плюс один кубик на 2 хода" и вернуться на главный экран игры . <br> 4. Кликнуть по кнопке броска кубика "пуск", увидеть, сумму двух кубиков. <br> 5. Проверить, что персонаж двигается на сумму выпавших чисел. <br> 6. Повторить шаги 4 и 5 еще раз (второй ход с двумя кубиками). <br> 7. Проверить, что на третий ход снова выпадает значение одного кубика. | При активации бонуса "Плюс один кубик на 2 хода" после броска кубика показана сумма двух кубиков вместо одной. Бонус действует два хода(выпавшие 7 и 8). Персонаж двигается на сумму - 7, при повторном броске - на 8. На третий бросок кубик показывает число 2. | При активации бонуса "Плюс один кубик на 2 хода" после броска кубика показана сумма двух кубиков. Персонаж двигается на сумму двух кубиков первый и второй ход после активации бонуса.
На третий бросок кубик показывает число одного кубика. |
| 9  | Проверка срабатывания двух бонусов одновременно "Плюс один кубик на 2 хода" и "Плюс два кубика на 2 хода"       | 1. Выполнить предусловие. <br> 2. Кликнуть на элемент "помогайки" справа, перейти в меню бонусов. <br> 3. Активировать бонусы "Плюс один кубик на 2 хода" и "Плюс два кубика на 2 хода". <br> 4. Кликнуть по кнопке броска кубика "пуск". <br> 5. Проверить, что персонаж двигается на сумму выпавших чисел. <br> 6. Повторить шаги 4 и 5 еще раз (второй ход с тремя кубиками). <br> 7. Проверить, что на третий ход снова выпадает значение одного кубика. | Персонаж движется на сумму выпавших чисел. Бонусы действуют два хода. На третий ход снова выпадает значение одного кубика. | Персонаж движется на сумму выпавших чисел. Бонусы действуют два хода. На третий ход снова выпадает значение одного кубика. |
| 10 | Проверка завершения игры                                                                                            | 1. Выполнить предусловие. <br> 2. Бросить кубик 10 раз. <br> 3. Проверить, что игра корректно завершается и вместо надписи кнопки "пуск" появляется надпись "получить попытки". <br> 4. Проверить, что после завершения игры нельзя совершать броски кубика. <br> 5. Проверить возможность активировать бонусы, кликнув на элемент "помогайки" справа и кликнув по бонусу "Плюс 1 кубик на 2 хода". | Игра корректно завершается и вместо надписи кнопки "пуск" появляется надпись "получить попытки". Нельзя совершать броски кубика после завершения игры. При клике на бонус помогайку после окончания игры он не активируется. | Игра корректно завершается и вместо надписи кнопки "пуск" появляется надпись "получить попытки". Нельзя совершать броски кубика после завершения игры. При клике на бонус помогайку после окончания игры он активируется. |


