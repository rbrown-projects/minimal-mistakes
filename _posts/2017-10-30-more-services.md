---
title:  "More Services"
search: true
categories: 
  - Software
---

Anybody in the enterprise space is subconsciously looking to minimize technical debt, going to sleep at night without worrying that they're building fragile spaghetti.  With many large, monolithic applications this is a pipe dream.  Even with promises of scalability and assurances of a Swiss watch architecture, it's impossible to objectively verify that your system isn't just a ball of mud.  Luckily, most of this hassle and worry can be avoided.


When designing a new architecture, it's easy to spend a lot of time architecting and thinking about how things fit together and interact "internally".  If a team is designing a CRM with reporting and billing features, you might imagine to overhear the following questions at the brainstorming session:

* How will we know that the billing module is grabbing the correct fields from the customer table in the CRM database?
* When should the reporting module update the billing table so the CRM can check that monthly_reports_run is true?
* How do we tell if the billing records in the reporting module is stale?


All of these questions have one thing in common: Over engineering.  Instead of worrying about the specifics of how one module is going to reach into another module and grab fresh data, the team should instead focus primarily on separating the modules into separate services which can be built, deployed and updated separately.  


Each service should have a well-defined interface that is independent of the system as a whole.  If you want to run monthly reporting, call an interface on the monthly reporting service that triggers a fetch of data at a predetermined time of day, as to not disrupt performance.  When it comes time for billing, instead of directly intruding into the customer tables, set up a mirrored instance that is synced daily that you can run billing off from.  Better yet, have a master service manage both billing and reporting on a certain day of the month.  With smaller services, you can focus less on the implementation and more on the big picture.

