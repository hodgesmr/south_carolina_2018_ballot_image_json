# South Carolina 2018 Ballot Image JSON

This repository contains JSON representations of the South Carolina Vote Image Log audit files (EL155) for the 2018 Statewide General Election. The [original audit files](https://www.scvotes.org/data/Audit2018General.html), provided by the South Carolina State Election Commission, are extracted from the ES&S Election System (Unity). The Unity file format is difficule to parse for analysis, so I've converted them to JSON.

The data in this repository, and provided by the state, show individual ballots and the votes cast on them. [No personal identifying information is included with the ballots](https://www.scvotes.org/data/AuditDesc.html).

>Vote Image Log is a copy of each ballot cast on an iVotronic machine. It lists the precinct and machine number associate with each ballot but does not indicate the time the ballot was cast or the voter casting the ballot

More information about what information is collected and disclosed in the South Carolina Election Audits can be found [on their website](https://www.scvotes.org/election-audits-south-carolina).

I make no guarantees regarding the accuracy of this data. It is presented as-is, from the time it was collected, parsed, and transformed from the South Carolina State Election Commission. All questions about integrity and permissible use should be directed to that office.

## Note about Bamberg County

There are two JSON files for Bamberg County: `Bamberg.json` and `Bamberg_Retabulated.json`.

The South Carolina State Election Commission [reported](https://www.scvotes.org/data/Audit2018General.html):

>An error was discovered in the certified results during post-certification analysis. A re-tabulation was performed and the errors were corrected. The error did not affect the outcome of any contests. The audit files and report from the re-tabulation are linked below. The data included in these files do not match the certified results in ENR as state law does not allow for corrections after certification. 

## A Matt Hodges project

This project is maintained by [@hodgesmr](http://twitter.com/hodgesmr).

_Please use it for good, not evil._
