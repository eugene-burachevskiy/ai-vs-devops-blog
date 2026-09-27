# Battle for Quality: OCR, CodeRabbit, PR-Agent, Codex. Honest evaluation.

It's the Autumn 2026 on the calendar. Almost a year, since agents fully fledged in the software development. A year ago at the autumn of 2025,  all popular harnesses were already existing (Claude Code, Codex and OpenCode all were launched in the middle of '25), but releases of Sonnet 4.5 and Opus 4.5 in autumn gave us ability to solve most of the complex tasks in a pair programming way. Same time released Grok 4.1 made the same agentic coding financially accessable. 
At the January of 2026, Andrej Karpaty wrote his known article "From vibe coding to agentic engineering", and since then more and more teams started fully adopting agentic coding and automations in day to day work. Right now not only OpenAI and Anthropic engineers are writing more then 80% of the code with agents, a lot of companies from fancy startups to moss enterprises are doing so. And while we are still adopting agentic engineering and inventing best practises, we are already having real challenges and bottlenecks. 
And one of the mostly challenging nowaydas - is the code review.

### Some hook here with interesting numbers about code review being a bottleneck as of Autumn 2026, find something, make cool hook

Coding became cheap. Teams are shrinking but amount of PR's these teams has to review, fix and improve, or make a thinkfull decision to deny, is growing and growing. We are often  treating agentic written code as a blockbox, since then CI/CD practises become a stape in most of the dev teams. So the simplest solution for review, low hanging fruit, is to implement an automated code review system in your CI/CD pipelines.

So do we. We are developing Exadel's flagship product offering - enterpirse ready coding agent names "Exadel-Colleague". But we are not a large team, 4 developers, 1 QA, 4 Forward Deploy Engineers. However we the help of fully integrated agentic coding practises we are still delivering ~100 Gitlab Merge Reqeusts and near 500 pipeline runs per each week, and this number is growing.

### History of our codex review pipeline

### How this pipeline works, what "diff only pipelie" means (I think we can call it so, because this is not a full agentic review), Structeured Output and json schemas. 

### Problems of pipeline, not a good prompt (I think focus on "how agent should speak" instead of "what agent should do" reduces quality of our review prompt, show examples). False positives make developers dont trust of review at all. Pipeline become a "secondary too" ,everybody is reviewing with own tools on own machines, codex advices sometimes are taken into account and fixed, but very often just skipped.

### That's why we decided to improve things. List what tools we decided to try and evaluate.

### Some interesting hook about these tools.

### Testing scenario and trategy of evaluation. Say that from one side comparison under some specific benchmark PR's would be good so we can evaluate numbers compared to another tools, but from other side we wanted to see real result on our codebase and on our own pipelines. The understanding how developers are comfortable to work with these tools is important key to success. 

### Tell about baseline. DeepSeek without tools, why we choose this? Why we cahnged later to Sol, even paying to attention that DS was crazy good?

### One week passed and we have a results. Give a initial number how much pipelines, lines of code we reviewed, how many runs did, how much tokens spent.

### >>> Stop here. We will continue later. <<<
