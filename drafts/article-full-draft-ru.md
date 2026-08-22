# От дорогого автокомплита, до полноценой AI Software Factory - что я вынес из Cursor FDE Bootcamp.

Представьте, Вы - Senior Forward Deployed Engineer.
Вы работаете с компанией Meridian Health. Исходные данные компании таковы:

- 4000 инженеров
- Adoption Cursor-а (ну или другого AI-coding агента) достиг 60% за первый месяц, но в последующие 5 месяцев цифры адопшена больше не росли
- PR velocity не растет
- При этом CTO очень хочет показать совету директоров рабочих cloud agents буквально через месяц
- 15 синьор инженеров в компании хотят доступ к SDK
- В компании уже есть concerns от секьюрити, из за доступа агентов к проду

И что в таком случае должен сделать опытный FDE? Помочь с ожидаемыми клауд агентами или SDK платформой? Или все же поставить под сомнение необходимость этих внедрений, потому что у компании все еще нет общей системы конфигураций, нет реальных улучшений workflow, а ботлнек по части код ревью после внедрения cloud agents станет еще серьезнее?

Несколько недель назад, в рамках партнерства нашей компании Exadel и Anysphere Cursor я проходил тренинг на Cursor FDE Bootcamp. И я думал, что он с большего будет о навороченных техниках имплементации AI в продуктах. Хотя первое же упражнение было о том, что делать не стоит. 

Как в примере выше, у кастомера была проблема не с наличием рабочих АИ агентов, у них была проблема с адопшеном технологии в процессы. Количество незакрытых PR в примере выше не уменьшилось бы с внедрением автономных агентов, а демо для боссов техническо было бы реальным, но организационно было бы просто фейком.

- **Поэтому первый важный скил FDE - это не строить системы быстро, а не строить быстро что-то на самом деле не нужное.**

И чтобы определить почему "Нет" может быть наболее технически верным ответом, мы должны взглянуть на то, что FDE на самом деле должен создавать.

[![Every customer is somewhere on the AI adoption curve](../images/cursor-fde-bootcamp/01-adoption-maturity-curve.jpg)](../images/cursor-fde-bootcamp/01-adoption-maturity-curve.jpg)

*Сaption: AI adoption is a progression from isolated tool use to a customer-owned software factory. The FDE’s job is to create sustainable movement, not activity inside one phase. Source: Cursor FDE Bootcamp v1, May 2026; publication permission required.*

FDE - это Adoption Engineer, это не тот человек который придет в компанию, внедрит новые модные технологии и покажет красивые демо. Его артифкаты - это не новый продукт, это "customer's new capabilities", способности и возможности клиента эффективно использовать и поддерживать новую технологию самостоятельно, после вас.

FDE объединяет несколько ролей:

- **Discovery:** find the workflow where AI can create measurable value.
- **Sequencing:** decide which capability the organization can sustain next.
- **Engineering:** ship a bounded working implementation in weeks, not quarters.
- **Governance:** make permissions, auditability, quality floors, and shutdown conditions concrete.
- **Change management:** build with internal engineers and turn skeptics into contributors.
- **Capability transfer:** ensure the customer can operate, modify, and extend the work.
- **Product feedback:** identify which custom patterns deserve to become reusable product primitives.


