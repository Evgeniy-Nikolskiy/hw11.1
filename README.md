# Homework 11.1

#### Выгода

##### Гибкая кастомизация метаданных для своих сервисов и других сущностей  

Все сущности, которые хранятся в Kubernetes являются его объектами. Он будет следить за состоянием объекта: что запущено, какие доступны ресурсы, как управлять приложением, перезапускать, обновлять. Удобно наличие аннотаций, которые служат для добавления собственных метаданных к объектам.

##### Быстрое и гибкое тестирование за счет возможности работать как с новым функционалом так и уже имеющимся

Тестирование и политики компании основной скелет для соблюдения SLA. Развертывание Kubernetes и его дольнейшая эксплуатация преполагает жесткую превязку команды к ввереному ей микросервису. Иметь возьможность откатить изменения в случае проблем, а также пройти и согласовать все этапы тесторвания помогает микросервису и команде в том числе не застревать на задачах и быстрее организовывать поставки, к примеру, новой фичи в бой, а также меньше подрываться по ночам.

##### Автоматическая балансировка нагрузки с помощью постоянного мониторинга

Как правило вопрос с балансировкой нагрузки решается на раннем этапе. Постоянный мониторинг увеличивает уровень контроля за микросервисами, что как следствие приводит к быстрому реагированию на возможные аварии, дефекты или даже их предотвращение.

##### Повышенная отказоустойчивость

В целом этот пункт является совокупностью всех вышеописанных действий при их строгом соблюдении.

##### Масштабируемость - cервисы распределяются между серверами в зависимости от потребностей

На мой взгляд масштабируемость самая хоатичная часть структуры. В зависимость от размера сервиса, необходимости в безопасности или наоборот в быстродействии распределение происходит на облачном хранилище одном или нескольких, железе в ближайшей серверной и т.д. Иметь возможность правильно распределить нагрузку при разумном учете нужд всегда хорошая идея и экономия для компании, но сложность заключается в том что к этому вопросу подключается несколько категорий специалистов. Те кто заведают инфраструктурой, кто следить за жизнью железа и стабильностью сети. В любом случае правильная организация коллектива во многих компаниях удачно с этим справляется, поэтому это однозначно плюс.

##### Простота развертывания - обусловлена небольшими, но частыми изменениями.

На простоту развертывания во многом влияет уровень связанности сервисов. В любом случае связанность будет ниже, чем в монолите, что в общем вытекает из названия организации инфраструктуры. Частые изменения необходимы для постоянной поддержки большой инфраструктуры в актуальном состоянии, её улучшении и быстром решении инцидентов, за счет облегченного расследывания инцидентов отдельной части структуры.

#### Проблемы

##### Существенные затраты на сопровождение

Это, думаю, самый очевидный пункт. Все описанные преимущества требуют отдельных команд, как следствие увеличение штаба сотрудников, траты на поддержку мониторинга, хранилищ, продуктов мониторинга, продуктов сбора логов, актуальности железа, не получится также сэкономить на всех остальных ресурсах необходимых микросервисам. Иначе стабильность их работы будет под вопросом как и сама затея уходить от монолита.  

##### Необходим более обширный мониторинг и постоянный контроль за ним

Обширный мониторнг, как было укзано в преимуществах, полезен для повышения реагирования на проблемы и отказаустойчивости в целом. С этим же приходит недостаток, что мониторинг нужен вообще для всего. С этим возникают проблемы так как каждая команда помимо собственных задач должна иметь хотябы поверхностные знания о том, чем занимаются их коллеги. А быть универсальным всегда большой труд.

##### Проблемы совместимостью API



##### Разбивка на сервисы единой инфраструктуры может создать большое количество изменений в инфраструктуре или отказ от успешно работающих ранее решений 
##### Усложненный сбор логов при большом количестве микросервисов