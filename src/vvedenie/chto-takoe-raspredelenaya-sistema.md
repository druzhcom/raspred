# Определение

`
Распределённая система - единосвязанная совокупность автономных электронно-вычислительных машин
`

### Автономная ЭВМ 

Машина способная работать независимо от других. Представляет собой `узел` или аппаратного обеспечения и\или программного. Способные действовать независимо друг от друга для достижения общих целей через обмен сообщениями друг с другом. Узел принимает сообщение, обрабатывает сообщение и передаёт сообщения дальше. Независимые узлы сами определяют временную последовательность взаимодействия с другими узлами. Поэтому в такой системе нет `глобальных часов` (термин). Поэтому есть необходимость к решению задач `синхронизации` и `координации`.

`Совокупность ЭВМ` значит, что может понадобиться регистрация, организация и управление списками узлов входящих и невходящих в распределенную систем. А также распределенние этимх списков по РС, чтобы узлы знали с кем общаться.

Управление членством в списке. Могут быть открытые и закрытые списки.

Открытые - любой участник может присредениться к РС и отправть сообщения другим участникам РС,
Закрытые - взаимодействовать могут только участники списка. Нужен отдельный механизм подключения и выхода из группы.

Контроль доступа. Нужен механизм аутентификации (может быть узким местом при масштабирования). Нужен механизм определения участником системы что он общается с нормальным узлом из списка, а не со злоумышленником. Нужен механизм конфиденциальности, чтобы недопустить раскрытия информации, если участник закрытого списка может общаться с участниками открытого списка.

РС часто организуется в видел `оверлейной сети`. Узел представляет собой программный комплекс и список участников, которым он может отправлять сообщения. Сообщения передаются по `TCP\IP`или `UDP` каналы.

Два типа Оверлейно сети:
1. Структурное наложение - каждый узел имеет четко определенный набор соседей с которыми он может общаться. Узлы организованы в видео `дерева` или `логического кольца`.
2. Не структурированое наложение - каждый узел имеет несколько ссылок на случайно выбранные другие узлы.

При оверлейной сети между двумя участниками всегда должны быть канал связи.по которому участники отправляют сообщения.

`Одноранговые сети (p2p)` - класс оверлейных сетей.

### Единоссвязанная 

Для пользователей распределенная система представляется единой системой. Таким образом узлы такой системы должны взаимодействовать между собой, чтобы пользователю казалось, что он работает с одной системой.

Узлами могут быть разные по мощности машины.

При этом, если отдельные части РС выходят из строя, РС должна продолжать действовать согласовано.

## Слой РС или посредническое ПО

В РС есть отедльный слой ПО, размещенный поверх ОС для помощи при разработке распределенных приложений. 

Архитектура распределенной системы состоит 
из:

- сети
- операционных систем на ЭВМ в сети
- Промежуточного слоя РС
- Интерфеймов ПсРС
- Приложений

ПсРС предоставляет средства для связи приложений. Скрывая различия в ОС и АО.
ПсРС предлагает единообразный интерфейс для различных приложений

ПсРС состоит из `менеджера ресурсов`, сетевых средств для связи взаимодействия приложений, услуг безопаности, услуг аккаунтинга, максировка сбоя и восстановление после сбоя.

ПсРС это набор частоиспользуемых функция необходимых для построения (распределенных) приложений.

### Функции: услуги связи

`Удалённый вызов процедур (RPC)` - общепринятая услуга в РС. Позволют приложению вызывать функцию, которая применяется и выполняется на удалённо компе. 

### Транзакции

Обычно приложения используют несколько сервисов РС. Поэотому ПсРС поддерживает атомарные транзакций, т.е. проведение операций по типу "всё или ничего". Таким образом ПсРС гарантирует что набор сервисов вызовётся все или не вызовется вообще.

### Композиция услуг

Сбор данных из разных сервисов и склеивание их. ПсРС позволяет генерировать поток данных и из последующее объединение. Также есть подход `mashup`: веб-страницы объединяющие и группирующие данные из разных истоников.


### Воспроизводимость

Приложение как группа процессов, в котором сообщение отправленное одним процессом гарантировано будет получено всеми или иникакими другими процессам.
