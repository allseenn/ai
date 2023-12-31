# Введение в ИИ

## Урок 1

### Историческая справка об ИИ

Вашей задачей в практическом занятии Темы 1 курса по основам Искусственного Интеллекта в GeekBrains будет взаимодействие с двумя древними ботами — ELIZA и SHRDLU. Пожалуйста, выполните следующие пункты:

1. Используйте адрес https://goo.gl/dbdskT для доступа к чат-боту ELIZA. Пообщайтесь с ней на английском языке. Попробуйте прочувствовать, как она реагирует на Ваши фразы, какие правила в ней имеются для этого.
2. Используйте адрес https://goo.gl/BRzGLo для получения пакета SHRDLU. Его необходимо скачать и развернуть на своём компьютере. Для Windows можно использовать только текстовую версию «text-only console version», либо можно скачать графический вариант «graphical 3-D version». Попробуйте при помощи команд манипулировать объектами этого виртуального мира.
3. В качестве дополнительного задания можно пообщаться с чат-ботом Натали, которая знает практически всё про Искусственный Интеллект.
   Сделать это можно в Телеграме по адресу https://goo.gl/UfBznc. Натали общается на русском языке. Попробуйте задавать ей различные вопросы. Попробуйте понять, как она устроена. Пришлите Вашу гипотезу об её устройстве преподавателю.

## Решение

### 1. ELIZA

ELIZA впервые появилась в 60-х годах, ее задача была эмулировать работу психотерапевта. По отзывам, некоторые люди думали, что общаются с настоящим человеком.
JS версия программы находится по адресу https://psych.fullerton.edu/MBIRNbAUM/psych101/Eliza.htm

Работает по моему лучше чем SHRDLU, не требует соблюдения строгой грамматики, наличия точки в конце предложения.

<img src=pics/05.png alt=i>

При просмотре исходного кода JavaScript, видим набор фраз (ответов), которыми владеет Элиза:

<img src=pics/06.png alt=s>

В ее арсенале всего 36 ключевых слов и 115 фраз.

Код является более простым чем SHRDLU и по сути представляет из себя поисковик по фразам, в соответствии с ключевыми словами, введенными пользователями.
Хранимые фразы, с помощью специальных функций, модифицируются, путем перестановки порядка слов.
В тоже время, есть функции, которые проверяют у получившихся предложений грамматику, время и пунктуацию.

### 2. SHRDLU

SHRDLU — это программа, созданная Терри Виноградом (Terry Winograd), американским ученым и профессором в области компьютерных наук, в конце 1968 годн. Программа SHRDLU была разработана в рамках исследований в области искусственного интеллекта (ИИ) на Массачусетском технологическом институте (MIT). Проект был разработан и использован в 1971 году при защите его диссертации "Процедуры как репрезентация данных в компьютерных программах для понимания естественного языка".

Основная цель программы состояла в исследовании возможностей компьютеров в понимании и выполнении команд на естественном языке, что является ключевой темой в области исследований искусственного интеллекта. SHRDLU оказала значительное влияние на развитие исследований в области обработки естественного языка и интерактивных систем.

Название "SHRDLU" представляет собой фонетическое произношение слова "геральд" (Gerald), которое было использовано в качестве одного из элементов в диалогах программы.

Программа SHRDLU была написана на языке программирования LISP (List Processing), который широко использовался в те времена для исследований в области искусственного интеллекта. SHRDLU демонстрировала способность взаимодействия с пользователем на естественном языке и манипулирования блоками в виртуальном мире, представляющем собой набор геометрических фигур.

Так как программа изначально запускалась на PDP-6 с маленьким монитором, то двухстороннее взаимодействие происходило с помощью текста. Позже появились графические варианты.

<img src=pics/01.png alt=r>

#### Анализ SHRDLU

Программу и ее исходный код можно скачать с личной страницы автора Терри Винограда, расположенной на сайте Стэндфордского университета https://hci.stanford.edu/winograd/shrdlu/

Консольная версия возвращает ответ в виде действий описанных текстом:

<img src=pics/02.png alt=o>

Существует графическая версия, использующая нативный код в Java обертке, реализованная студентами университета:

<img src=pics/03.png alt=s>

Набор команд и действий у двух вышеописанных версий одинаков.
Разработчик пытался сделать программу работающую на естественном английском языке. Что вызывает трудности у иностранца, который, например привык к командам юникс или инструкциям на языках программирования.

По сути составление команды сводится к написанию предложения с обязательной точкой в конце. Что гораздо сложнее работы в терминале линукса, который подскажет с помощью таба недостающую часть. Либо с помощью встроенной справки можно посмотреть список команд и их описание.
В SHRDLU таких возможностей не предусмотренно. Более того наблюдается небольшой словарный запас.

<img src=pics/04.png alt=t>

Как видно из рисунка для поднятия предмета - нужно применить глагол Pick up, далее необходимо указать не просто фигуру, а также ее цвет и размер.

Т.е. если у нас будет один большой зеленый квадрат, то фраза "Подними зеленый квадрат" будет недостаточной.

Программа не прощает ошибок. Если ввести предложение без точки, то она зависает.

При просмотре исходного кода программы, видно, что она обладает большим функционалом, и больше похожа на интерпретатор LISP

Существует большое количество вариаций и копий на тему данной программы.

Наиболее удачной версией, на мой взгляд, является игра написанная по мотивам и на движке SHRDLU -

https://braingames.santiontanon.dev/games/shrdlu/v39/shrdlu.html

### 3. ТГМБот Натали

Более новая и более продвинутая версия.
Но, не разговаривает на английском языке - языке IT и AI.
Постоянно говорит про Романа Душкина ))

<img src=pics/07.png alt=l>

Бот не поддерживается, т.к. ссылки на сайт и канал в ютюбе ai101.ru не принадлежат больше владельцу.

<img src=pics/08.png alt=a>

Но, в вебархиве прежний сайт о ИИ остался:

<img src=pics/09.png alt=v>

Телеграм бот Натали функционирует, потому же принципу, что и Eliza. Есть определенный набор фраз, которые генерируются на определенные ключевые слова.

Но, т.к. проект, судя по архиву, заброшен несколько лет назад, он не был уникальным и передовым.

Перечисленные выше источники и программы не являются нейросетями и тем более искусственным интеллектом.
