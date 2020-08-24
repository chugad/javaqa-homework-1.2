# Отчёт о тестировании приложения Credit Card Number Validator

## Краткое описание

24.08.2020 было проведено функциональное тестирование приложения Credit Card Number Validator на предмет проверки валидации кредитных карт.

На тестирование затрачено: 3 часа

В результате тестирования выявлен один дефект: https://github.com/chugad/javaqa-homework-1.2/issues/1.
## Описание процесса тестирования

В процессе тестирования артефакты не использовались, так как тестирование производилось исследовательским методом, а так же методом граничных значений для номеров кредитных карт. По окончании тестирования как артефакт можно выделить данный отчет о тестировании и выявленный дефект.

В качестве тестовых данных для проверки валидных номеров кредитных карт использовались данные сгенерированные на сайте [freeformatter.com](https://www.freeformatter.com/credit-card-number-generator-validator.html). 
Пример:
* 4003622357144245
* 5411057186814960
* 5582757995846045
* 3544461911836014
* 30077998942876

Ожидаемый результат будет выглядеть следующим образом:
```"C:\Program Files\AdoptOpenJDK\jdk-11.0.8.10-hotspot\bin\java.exe" -javaagent:C:\Users\chuga\AppData\Local\JetBrains\Toolbox\apps\IDEA-C\ch-0\202.6397.94\lib\idea_rt.jar=53438:C:\Users\chuga\AppData\Local\JetBrains\Toolbox\apps\IDEA-C\ch-0\202.6397.94\bin -Dfile.encoding=UTF-8 -classpath C:\Users\chuga\IdeaProjects\untitled\out\production\untitled Main
Result is OK

Process finished with exit code 0
```
где `OK` означает, что номер валидный.

В качестве тестовых данных для проверки невалидных номеров кредитных карт вручную сгенерированы невалидные номера карт. 
Пример:

1. Пустое поле без символов
2. 1                      *граничное значение 1 символ*
3. 123456789112345        *граничное значение 15 символов*
4. 12345678911234567      *граничное значение 17 символов*
5. йцукфываячсмйцук       *буквы русског алфавита*
6. qwerasdfzxcvqwer       *буквы английского алфавита*
7. "№;%:?*()_+!?*()       *специальные символы*

Ожидаемый результат будет выглядеть следующим образом:
```"C:\Program Files\AdoptOpenJDK\jdk-11.0.8.10-hotspot\bin\java.exe" -javaagent:C:\Users\chuga\AppData\Local\JetBrains\Toolbox\apps\IDEA-C\ch-0\202.6397.94\lib\idea_rt.jar=62060:C:\Users\chuga\AppData\Local\JetBrains\Toolbox\apps\IDEA-C\ch-0\202.6397.94\bin -Dfile.encoding=UTF-8 -classpath C:\Users\chuga\IdeaProjects\untitled\out\production\untitled Main
Result is FAIL

Process finished with exit code 0
```
где `FAIL` означает, что номер невалидный.

Тестирование производилось в следующем окружении:
* Устройство: Windows 10 x64
* Браузер: Яндекс.Браузер Версия 20.8.0.894 (64-bit)
