---
title:  "Code Coverage"
search: true
categories: 
  - Software
---

While 100% code coverage might appear to be a clear mandate, it's often a lofty ideal and a black hole for your development team.  Picture this all too common scenario:

* User story is groomed and placed in sprint, assigned to a developer (lets call him Alan).
* Alan drafts a brilliant, simple solution, but after engaging in a brief conversation with a fellow team member (lets call her Tina), learns that the story effectively removes existing functionality from the system.  Tina had completed this work over 5 months ago and recalls writing a comprehensive test suite. 
* Tina acknowledges her solution might have been a bit over engineered, and this doesn't deter Alan from making his changes.  When Alan runs Tina's test suite, he sees that approximately 1/4 of Tina's tests fail, while the remaining half pass.  Out of the passing tests, around half of those no longer make sense.  
* Pursuing 100% coverage, Alan spends more time fixing Tina's old unit tests than he spends delivering what the business originally asked for.


Sound familiar?  Let me be clear:  Unit testing is incredibly useful.  Automated end-to-end testing is also invaluable and saves extraordinary amounts of time.  Attempting to anticipate all possible inputs to your system is impossible and cost-benefits wise, a waste of resources (unless perhaps, your code is launching the space shuttle).  Tina had good intentions but failed to use her time wisely.  


Instead of thinking about the short-term benefits of systematically verifying her own work (which she should be able to do herself, since she wrote it), Tina should have considered the tech debt she created for Alan to clean up.  Tina assumed that the unit testing would pay off, but it's entirely possible that it just wasted project resources.  Programmers should instead focus on developing solutions that can be verified through as few tests as possible.  


This may requires substantial forethought, but the simplest way to achieve stability is to create small, testable components.  A fellow developer should be able to read your code and understand what it does; It shouldn't take more than a few days for a developer to understand what's important.  If tests make your code more readable, then write them.  Otherwise, leave them out until you really need them.