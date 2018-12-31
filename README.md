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

## Format

Every county file has its ballot scans organized by precinct. Each ballot scan contains the keys: `ballot index`, `iVotronic Serial Number`, and `votes`. The `ballot index` value indicates which ballot style that appears in the precinct was used to cast that ballot. The ballot index can be different in each precinct for a ballot style that is common to the precinct. The `votes` object contains the key `straight party` to indicate if the ballot was cast as a straighy party vote, and for which party, if applicable. The other keys within the `votes` object vary based on which contests were present on the ballot, and how the voter chose to participate.

```json
{
    "precincts": {
        "101 - Stone Church": [
            {
                "ballot index": "2",
                "iVotronic Serial Number": "5110314",
                "votes": {
                    "straight party": {
                        "selected": true,
                        "party": "Republican"
                    },
                    "Governor and Lieutenant Governor": "Henry McMaster",
                    "Secretary of State": "Mark Hammond",
                    "State Treasurer": "Curtis Loftis",
                    "Attorney General": "Alan Wilson",
                    "Comptroller General": "Richard Eckstrom",
                    "State Superintendent of Education": "Molly Mitchell Spearman",
                    "Commissioner of Agriculture": "Hugh Weathers",
                    "CON0003 U.S. House of Representatives": "Jeff Duncan",
                    "HOU0003 State House of Representatives": "Gary Clary",
                    "Solicitor Circuit 13": "Walt Wilkins",
                    "Probate Judge": "David K Allison",
                    "CCL0001 County Council": "Ensley Feemster",
                    "Amendment 1": "Yes",
                    "MUN0566 City Council": "Robert Halfacre",
                    "MUN0566 City of Clemson Beer and Wine Sales": "Yes, In favor of the question"
                }
            },
            {
                "ballot index": "2",
                "iVotronic Serial Number": "5110314",
                "votes": {
                    "straight party": {
                        "selected": false,
                        "party": null
                    },
                    "Governor and Lieutenant Governor": "Henry McMaster",
                    "Secretary of State": "Mark Hammond",
                    "State Treasurer": "Curtis Loftis",
                    "Attorney General": "Alan Wilson",
                    "Comptroller General": "Richard Eckstrom",
                    "State Superintendent of Education": "Molly Mitchell Spearman",
                    "Commissioner of Agriculture": "Hugh Weathers",
                    "CON0003 U.S. House of Representatives": "Jeff Duncan",
                    "HOU0003 State House of Representatives": "Gary Clary",
                    "Solicitor Circuit 13": "Walt Wilkins",
                    "Probate Judge": "David K Allison",
                    "CCL0001 County Council": "Ensley Feemster",
                    "Amendment 1": "Yes",
                    "MUN0566 City Council": "Robert Halfacre",
                    "MUN0566 City of Clemson Beer and Wine Sales": "No, Opposed to the question"
                }
            }
        ]
    }
}
```

## A Matt Hodges project

This project is maintained by [@hodgesmr](http://twitter.com/hodgesmr).

_Please use it for good, not evil._
