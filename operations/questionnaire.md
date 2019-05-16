---
title: Ops Questionnaire
---
# How to use this questionnaire

This questionnaire is big. Many of the questions are open-ended, and most probably require research and team discussion. Trying to come up with the perfect answer to every question for every service will likely be overwhelming.

These questions are sorted by a combination of feelings and my own experience. The intent is for earlier questions to be necessary for every service, while later questions are less important for non-critical services. The order is not strictly defined, and when in doubt, you should defer to your own judgement and the particulars of the service that you’re evaluating.

However, pay particular attention to the first two questions: Who are the stakeholders, and what is the objective? Some applications simply do not need to be bulletproof, scale to millions of users, or have 99.999% uptime. Your objective and your stakeholders should determine what is an acceptable answer to the rest of the questions.

# What is the objective?

* What problem does this service solve?
* Who or what is impacted if that problem is not solved?

# Who are the stakeholders?

* Who, or what team, is considered the owner of this service?
* Who, or what team, is responsible for administering this service? (User accounts, permissions?)
* Who, or what team, is responsible for operating this service? (Deployments, migrations, disaster recovery?)
* Who are the users of this service? Are there different kinds of users? Do they need to be treated differently?
* What voice does each of these stakeholders have in the development and operations process?

# How will it be tested?

* Are there unit tests? Are they automated?
* Are there integration tests? Are they automated?
* Will the application be deployed to multiple environments for different types of testing?
* Is there a QA team that will be testing? Will they be blocked if their environment is down?

# How will it be packaged?

* Tar files? Zip files?
* System packages?
* Containers?

# How will it be configured?

* What config files are required?
* Is there static data in databases that needs to be seeded?
* Does the configuration change between different environments? (Development? Testing? Staging? Production?)

# How will it be discovered?

* What URL or DNS name will it be accessible under?
* What port will clients use to connect to it?
* Do clients depend on an external system to discover it?

# How will it be secured?

* Is it accessible from the internet?
* What does legitimate traffic look like?
* What sensitive information does this service handle? (HIPAA? PCI?)
* How is access audited or logged?

# How will it fail?

* What types of failures are possible?
* What types of failures are expected?
* How will those types of failures be reported to its consumers?
* How should those consumers handle those types of failures?
* How will those types of failures be reported to other stakeholders? (Owners? Operators? Administrators?)
* How will those stakeholders respond to those types of failures? Is there a runbook?
* What is the service’s MTBF (Mean Time Between Failures)?

## Responding to failures:

* Are there other “hot” instances that can pick up the slack?
* Are there other regions that can pick up the slack?
* During an outage, who is the incident leader? Who handles communication with affected stakeholders? Are they different people?
* After a failure, what is the agenda for the blameless postmortem?

# What is the disaster recovery plan?

* How will the data be backed up? How often do we test restoring those backups?
* Are backups stored in multiple locations? What happens if a set of backups is destroyed?
* Is there a single incident that could take out the “online” data and all of its backups?
* What is the agenda for the postmortem?
* Are you able to tell what users are affected by an outage?
* Do you have a plan for communicating the impact of an outage to stakeholders? (Affected users? Product development? Marketing?)
* What is the service’s MTTR (Mean Time To Repair)?

# How will it be upgraded?

* Does it store local state? How does it recover when that state disappears?
* How do you stop the service safely? Can it stop at a moment’s notice, or does it need to finish active work?
* How are database migrations executed?
* Will database migrations be backward compatible with old application versions?
* Is there a deprecation policy for any APIs that the application provides?
* How much downtime is expected? How much downtime is acceptable?

# How will it be consumed?

* Who will be consuming it?
* Where will they find documentation?
* What ports will it be listening on? (Port, protocol, source of traffic)
* Does it have a REST API?
* Does it use websockets?
* Does it serve HTML to the browser?
* Does it serve static files?
* Does it include “workers” that consume from a queue of some kind?
* Does it include “cron” style scheduled tasks?
* Does it maintain other kinds of persistent connections?

# How do you administer it?

* Is there a user interface? If so, how does an administrator/developer access it?
* Where is the runbook?
* Can those runbook tasks be run at any time, or only during a maintenance window?
* Does the runbook include stakeholders who need to be notified before a task is executed?
* Is there any known future work? Who will do it, and how will they be reminded? (Certificates expiring, re-evaluating scale…)

# What does it depend on?

* What library dependencies does it depend on? What versions are they pinned to?
* Does it require databases? Caches? Other services or APIs?
* Does it maintain persistent network connections? What is the reconnect logic if those connections are interrupted?
* How will it handle failures in each of those dependencies?
* Does it require external dependencies that need to be renewed? (Certificates? Payment methods?) Who is responsible for renewal? How will they keep that schedule?

# How will it be monitored/measured?

* What will the application spend most of its time doing?
* Is that work measured?
* Where will those measurements be sent?

# How will it alert stakeholders to failures?

* What are the types of alerts? Are some more severe than others?
* When someone receives an alert, will they be able to do something about it immediately?
* If there’s nothing to do, does it need to be an alert? (Avoid building a habit of ignoring alerts.)
* Does someone get woken up if an alert fires in the middle of the night? Is it a rotating group of people?

# What is the SLA?

* Is there a maintenance window?
* How is “uptime” defined and measured?
* What constitutes an “unacceptable” amount of downtime?
* What is the impact of an “unacceptable” amount of downtime?
* Are there metrics that might indicate that the service is about to fail?

## If the service consumes from a queue:

* How does the system handle a message that can’t be processed?
* How will a queue backlog impact other parts of the system?

## If the service is a scheduled task

* How does the system handle a failed run?
* Is there a number of consecutive failed runs that would be a serious problem?
* How does the system react if a run doesn’t even start? (i.e. The task is disabled.)

# How will it scale?

* What are the areas of growth?
* Will those areas see 10x the current amount of data? 100x? 1000x?
* What are the estimates for those areas of growth? When will those estimates be re-evaluated?
* Do your answers to this questionnaire serve the objective?
* Is the amount of effort proportional to the benefit of solving this problem?

# Further reading

* [Creating a Microservice? Answer these 10 Questions First](https://www.datawire.io/creating-a-microservice-answer-these-10-questions-first/)
* [Heroku Isn’t for Idiots](https://www.rdegges.com/2012/heroku-isnt-for-idiots/)
* [“A few questions to consider”](https://monkey.org/~marius/checklist.pdf)

# Thanks to everyone who contributed

* [@edropple](https://twitter.com/edropple)
* [@savant](https://twitter.com/savant)
* [@kristianvanders](https://twitter.com/kristianvanders)
* [@mhkid](https://twitter.com/mhkid)
* [@rnelson0](https://twitter.com/rnelson0)
