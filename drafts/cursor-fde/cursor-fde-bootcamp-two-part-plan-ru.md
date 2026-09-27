# Cursor FDE Bootcamp: high-level план двух статей

> **Формат:** дилогия на русском языке  
> **Общий замысел:** первая статья объясняет, как FDE диагностирует готовность компании и выбирает правильный следующий шаг; вторая показывает, как выбрать, построить и оценить конкретную AI automation или agent platform.  
> **Целевой размер:** примерно 2 800–3 500 слов на каждую часть.

---

## Почему две статьи, а не одна или три

Текущий draft уже содержит около 2 000 слов и охватывает только вступление, роль FDE и две оси диагностики. Если реализовать весь исходный план в одной публикации, статья легко превысит 6 000 слов и потеряет темп.

Две части дают естественную границу:

1. **Как понять, что клиенту действительно нужно и готов ли он это поддерживать?**
2. **Как выбрать, построить и оценить правильное AI-решение?**

Третья часть потребовалась бы только при значительном расширении технического материала про Cursor SDK runtime, hosted/self-hosted deployment, secrets, egress, networking, observability и security. Тогда это была бы уже отдельная статья про Cursor platform engineering, а не продолжение bootcamp retrospective.

---

# Часть 1. Как понять, готова ли компания к AI agents

## Рабочий заголовок

**От дорогого autocomplete к AI Software Factory: как FDE диагностирует готовность компании**

Альтернативный вариант:

**Почему компании просят AI agents раньше, чем становятся к ним готовы**

## Главный вопрос

> Как определить, какое AI-внедрение действительно нужно клиенту и сможет ли организация поддерживать его после ухода FDE?

## Обещание читателю

После первой части читатель должен уметь:

- отличать использование AI tools от реального organizational adoption;
- понимать роль FDE как Adoption Engineer;
- оценивать клиента по AI maturity и SDLC shape;
- замечать organizational blockers вместе с техническими;
- определять, когда Cloud Agents преждевременны;
- понимать, из чего состоит Enterprise Readiness и scaffolding.

## Структура

### 1. Meridian Health: клиент просит Cloud Agents, но правильный ответ может быть «нет»

- 4 000 инженеров.
- Adoption достиг 60% и перестал расти.
- PR velocity не улучшился.
- Review cycle остается длинным.
- CTO хочет показать Cloud Agents совету директоров.
- Senior engineers хотят SDK.
- Security уже выражает concerns.

Главный reframe:

> У клиента может быть не дефицит AI agents, а проблема с adoption системы в реальные engineering processes.

Важно явно сказать, что Meridian Health является training scenario, а не подтвержденным production customer case.

### 2. Что на самом деле создает FDE

- FDE как Adoption Engineer.
- Артефакт engagement не равен конечному результату.
- Результат: новая capability клиента, которую он способен поддерживать самостоятельно.
- Discovery.
- Sequencing.
- Engineering.
- Governance.
- Change management.
- Capability transfer.
- Product feedback.

Личная линия:

- ожидание product training про agents, rules и SDK;
- неожиданное переключение на процессы, ownership и реальные ограничения бизнеса;
- изменение собственного понимания роли FDE.

### 3. Чем FDE отличается от соседних ролей

Сравнить:

- Solution Engineering;
- Consulting;
- Staff Augmentation;
- Product Engineering;
- Forward Deployed Engineering.

Ключевой вывод:

> То, что для другой роли может быть финальным критерием успеха, для FDE часто является только checkpoint.

### 4. Organizational architecture

- Executive sponsorship как часть архитектуры.
- Org chart как часть system design.
- Compliance и ownership boundaries.
- Почему отсутствие нужного stakeholder может быть серьезнее отсутствующей API integration.
- Принцип `build with, not for`.
- Почему customer engineers должны участвовать в discovery, implementation и final demo.

### 5. FDE outcome test

Перед началом engagement спросить:

1. Что нового клиент сможет делать после нашего ухода?
2. Кто станет owner-ом результата?
3. Что докажет изменение реального workflow, а не только создание demo?
4. Сможет ли клиент самостоятельно построить следующий instance решения?

### 6. Две оси диагностики

#### AI maturity

Определяет, какую сложность организация способна поддерживать:

1. AI почти не встроен в ежедневную разработку.
2. Autocomplete и отдельные power users.
3. Общие synchronous agentic workflows, rules и guardrails.
4. Async agents и automations.
5. Customer-owned agent platform или AI Software Factory.

Главный тезис:

> Active seats показывают доступ к инструменту, но не зрелость adoption.

#### SDLC shape

Показывает, где именно AI встроен в lifecycle:

```text
Plan → Design → Write → Review → Test → Deploy
```

Нужно найти:

- где работа ожидает человека;
- где находится реальный bottleneck;
- где ускорение одного этапа создало очередь на следующем;
- какой этап даст измеримый engineering outcome.

Короткая формула:

> **Maturity определяет, что организация сможет удержать, а SDLC shape показывает, куда имеет смысл вмешиваться.**

### 7. Scaffolding before autonomy

Workshop scenario: Northstar Logistics.

Исходное состояние:

- высокая доля active Cursor users;
- большие различия между командами;
- нет центральных rules или sub-agents;
- нет shared configuration repository.

Enterprise Readiness engagement:

- изучить работу лучших внутренних команд;
- извлечь повторяемые patterns;
- создать 6–10 high-leverage rules;
- создать несколько narrow sub-agents;
- поместить конфигурацию в shared, versioned repository;
- провести teach-back sessions;
- назначить owner-а;
- оставить внутренних инженеров способными поддерживать систему.

Важно объяснить, что rules нельзя писать из теории. Их нужно извлекать из реальной работы сильных внутренних команд.

### 8. Readiness checklist

Перед переходом к async agents проверить:

- Есть ли общие и versioned patterns?
- Определены ли contribution и review ownership?
- Есть ли engineering baseline?
- Понимают ли команды quality gates?
- Есть ли accountable engineering leader?
- Участвуют ли respected skeptics?
- Может ли downstream review process обработать увеличившийся output?
- Кто будет поддерживать систему после handoff?

### 9. Финал первой части

Основной вывод:

> Большинству компаний, которые просят Cloud Agents, сначала нужен нормальный scaffolding.

Cloud Agents не исправят:

- различия между командами;
- отсутствие ownership;
- нестабильные review practices;
- непонятные permissions;
- отсутствие общего engineering workflow.

Они просто начнут воспроизводить эти проблемы быстрее.

## Целевой объем

Примерно **2 800–3 200 слов**.

Это сопоставимо с опубликованными deep dive статьями:

- Kubernetes Agent Sandbox: около 3 130 слов;
- Advanced LLM/AI Engineering: около 3 270 слов.

## Images

1. `01-adoption-maturity-curve.jpg`
2. `02-pillars-across-maturity.jpg`
3. `03-same-maturity-different-sdlc.jpg`
4. `04-readiness-training-scenario.jpg`

Все подписи под screenshots оставить на английском.

---

# Часть 2. Как выбрать первую automation и не построить demo вместо platform

## Рабочий заголовок

**От первого AI workflow до agent platform: практические уроки Cursor FDE Bootcamp**

Альтернативный вариант:

**Вы не построили AI platform, если второй agent все еще требует консультанта**

## Главный вопрос

> Как выбрать правильную первую automation, измерить ее реальную ценность и оставить клиенту capability, а не зависимость от FDE?

## Обещание читателю

После второй части читатель должен уметь:

- выбирать первый automation use case по value и failure cost;
- проектировать quality floors и shutdown conditions;
- отличать auditability от correctness;
- выбирать между Automation, SDK и internal agent platform;
- определять platform readiness;
- оценивать не только agent output, но и capability transfer;
- понимать, почему customer ownership является частью production readiness.

## Структура

### 1. Короткий мост из первой части

Напомнить:

- maturity определяет допустимую сложность;
- SDLC shape определяет точку вмешательства;
- async work имеет смысл только после scaffolding;
- теперь нужно выбрать первый bounded use case.

Не пересказывать всю первую статью. Достаточно 2–3 коротких абзацев и ссылки.

### 2. Как выбрать первую automation

Оценивать кандидатов по следующим критериям:

1. Frequency.
2. Human toil.
3. Scope boundedness.
4. Existing instrumentation.
5. Failure cost.
6. Human reviewability.
7. Time to first value.
8. Named ownership.
9. Required permissions.
10. Reusability as a pattern for the next automation.

Главный тезис:

> Первая automation должна выбираться по стоимости ошибки и возможности проверить результат, а не по эффектности demo.

### 3. Flaky-test triage scenario

Workshop scenario Northstar Logistics, несколько недель после Enterprise Readiness.

Показать progression:

- shared configuration foundation уже используется командами;
- появились ownership и contribution;
- есть measurable bottleneck;
- существует flake-rate dashboard;
- use case можно ограничить одним test runner;
- рабочую версию можно проверить на bounded scope.

Главная ошибка initial proposal:

- измерять только overall accuracy.

Более правильный launch gate:

- считать dangerous false classification;
- особенно внимательно измерять случаи, когда реальная regression ошибочно объявляется flaky test.

Вывод:

> Overall accuracy часто выбирают тогда, когда еще не определена стоимость разных типов ошибки.

### 4. Regulated workflow и human sign-off

Workshop scenario Anchor Bank:

- агент читает diff, commit history и Jira ticket;
- готовит business justification, risk summary и reviewer routing;
- публикует draft;
- человек редактирует и подписывает результат.

Явные exclusions:

- no auto-approval;
- no agent sign-off;
- no cross-repository dependency analysis в v1.

Главный тезис:

> В regulated software правильной первой задачей AI может быть подготовка evidence для ответственного человеческого решения, а не замена этого решения.

### 5. Quality floors, escape hatches и shutdown conditions

Определить заранее:

- минимально допустимое качество;
- manual override;
- rollback procedure;
- excluded repositories;
- условия временной приостановки automation;
- условия полного отключения;
- критерии rescope или прекращения engagement.

Важно различать:

- shutdown конкретной automation;
- rollback на предыдущий workflow;
- stop/go decision для всего engagement.

### 6. Auditability не равна correctness

Workshop scenario с cross-service configuration PRs:

- audit trail показывает, что сделал agent;
- он не доказывает, что изменения правильные;
- success criteria должны включать correctness, а не только полноту audit log и сокращение времени.

Короткий тезис:

> **An audit trail proves what the agent did. It does not prove the result was correct.**

### 7. Automation, SDK или platform

Использовать Automation, когда запрос звучит так:

- on every PR;
- every morning;
- when CI fails;
- when a Sentry issue appears;
- send the result to Slack.

Рассматривать SDK, когда:

- agent встроен в продукт клиента;
- нужен custom UX;
- пользователи взаимодействуют с agent внутри customer application;
- требуется полный lifecycle или streaming control;
- настоящий platform team строит shared runtime для нескольких consuming teams.

Рассматривать AI SDLC Integration, когда проблема распределена по стадиям Plan, Design, Test или Deploy, но клиент не строит reusable platform.

### 8. Platform readiness

Перед internal agent platform проверить:

- существует ли настоящий platform team;
- участвует ли platform lead;
- есть ли 2–3 consuming teams;
- включены ли auth, observability, evaluation и governance;
- может ли consuming team расширить reference agent;
- способен ли platform team построить второй agent без FDE.

### 9. Second-agent test

Workshop scenario Northstar Logistics спустя несколько месяцев:

- первый production agent уже работает;
- DevEx team самостоятельно создает следующие agents;
- несколько product teams хотят собственные use cases;
- появляется реальная потребность в shared platform primitives.

Главный вывод второй статьи:

> **Если клиент не может построить второй agent без вас, вы построили один agent, а не platform.**

### 10. Как измерять результат engagement

Использовать цепочку:

```text
Adoption signal → Engineering outcome → Business outcome → Capability transfer
```

#### Adoption signal

- команды регулярно используют workflow;
- reviewers взаимодействуют с output;
- внутренние engineers меняют rules и integrations.

#### Engineering outcome

- review turnaround;
- maintenance toil;
- onboarding lead time;
- defect rate;
- release cycle.

#### Business outcome

- более быстрое onboarding клиентов;
- меньше compliance effort;
- более надежные releases;
- меньшая operational load.

#### Capability transfer

- named owner;
- runbook;
- shutdown procedure;
- customer team проводит final demo;
- внутренние engineers реализуют extension;
- следующий use case scoped до handoff.

### 11. Change management и customer ownership

- respected practitioners как источник patterns;
- skeptics как диагностический сигнал;
- teach-back вместо одностороннего training;
- customer engineers должны спорить и менять implementation;
- downstream процессы нужно перестраивать, если AI увеличивает upstream throughput;
- 30/60/90-day ownership plan.

### 12. Финал второй части

Вернуться к основной мысли всей дилогии:

> Первый agent доказывает, что технология может работать. Второй agent, построенный и поддерживаемый самим клиентом, доказывает, что engagement сработал.

Финальная формула:

> **The FDE’s real deliverable is customer independence.**

## Целевой объем

Примерно **3 000–3 500 слов**.

Не углубляться в Cursor SDK runtime, networking и security internals сильнее, чем требуется для выбора архитектуры. Эти темы могут стать отдельной технической публикацией.

## Images

1. `05-first-automation-training-scenario.jpg`
2. `06-regulated-workflow-training-scenario.jpg`
3. `07-sdk-vs-automation.jpg`
4. `08-platform-readiness-training-scenario.jpg`
5. `09-customer-ownership.jpg`

Все подписи под screenshots оставить на английском.

---

# Правила использования workshop scenarios

Northstar Logistics, Anchor Bank, Meridian Health и другие организации в deck выглядят как synthetic, composite или anonymized workshop scenarios. Пока нет отдельного подтверждения, их нельзя представлять как реальные production customer stories.

Безопасная формулировка:

> На bootcamp мы разбирали сценарий банка, в котором senior engineers тратили около 20 часов в неделю на подготовку SOX documentation.

Небезопасная формулировка:

> Cursor внедрил в Anchor Bank automation, которая сократила затраты на SOX documentation на 50%.

Числа из scenarios нужно описывать как:

- условия упражнения;
- proposed targets;
- success criteria;
- simulated progression;
- материал для обсуждения правильного scope или metrics.

Не описывать их как подтвержденные production results без независимого источника.

---

# Общая narrative arc

```text
Часть 1
Клиент просит advanced AI
        ↓
FDE ставит запрос под сомнение
        ↓
Диагностирует maturity и SDLC shape
        ↓
Обнаруживает missing scaffolding
        ↓
Готовит организацию к безопасной automation

Часть 2
Организация готова к bounded automation
        ↓
FDE выбирает use case по value и failure cost
        ↓
Определяет metrics, quality floor и shutdown conditions
        ↓
Выбирает Automation, SDK или platform
        ↓
Передает ownership клиенту
        ↓
Клиент самостоятельно строит второй agent
```

Общий вывод дилогии:

> **FDE не просто внедряет AI. Он помогает организации перейти на следующий устойчивый уровень и доказывает, что она сможет продолжать без него.**
