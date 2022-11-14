# South Carolina 2018 Ballot Image JSON

This repository contains JSON representations of the South Carolina Vote Image Log audit files (EL155) for the 2018 Statewide General Election. The [original audit files](https://web.archive.org/web/20190330063225/https://www.scvotes.org/data/Audit2018General.html), provided by the South Carolina State Election Commission, are extracted from the ES&S Election System (Unity). The Unity file format is difficult to parse for analysis, so I've converted them to JSON.

The data in this repository, and provided by the state, show individual ballots and the votes cast on them. [No personal identifying information is included with the ballots](https://web.archive.org/web/20190330063157/https://www.scvotes.org/data/AuditDesc.html).

>Vote Image Log is a copy of each ballot cast on an iVotronic machine. It lists the precinct and machine number associate with each ballot but does not indicate the time the ballot was cast or the voter casting the ballot

More information about what information is collected and disclosed in the South Carolina Election Audits can be found [on their website](https://web.archive.org/web/20190330061926/https://www.scvotes.org/election-audits-south-carolina/).

I make no guarantees regarding the accuracy of this data. It is presented as-is, from the time it was collected, parsed, and transformed from the South Carolina State Election Commission. All questions about integrity and permissible use should be directed to that office.

## Note about Bamberg County

There are two JSON files for Bamberg County: `Bamberg.json` and `Bamberg_Retabulated.json`.

The South Carolina State Election Commission [reported](https://www.scvotes.org/data/Audit2018General.html):

>An error was discovered in the certified results during post-certification analysis. A re-tabulation was performed and the errors were corrected. The error did not affect the outcome of any contests. The audit files and report from the re-tabulation are linked below. The data included in these files do not match the certified results in ENR as state law does not allow for corrections after certification.

## Format

Every county file has its ballot scans organized by precinct. Each ballot scan contains the keys: `ballot index`, `iVotronic Serial Number`, and `votes`. The `ballot index` value indicates which ballot style that appears in the precinct was used to cast that ballot. The ballot index can be different in each precinct for a ballot style that is common to the precinct. The `votes` object contains the key `straight party` to indicate if the ballot was cast as a straight party vote, and for which party, if applicable. The other keys within the `votes` object vary based on which contests were present on the ballot, and how the voter chose to participate.

```json
{
    "precincts": {
        "101 - Stone Church": [
            {
                "ballot index": 2,
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
                "ballot index": 2,
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

## Directory Structure

Due to GitHub's file size limit, the county JSON files are compressed into four Zip archives.

```
counties/
├── 01_12.zip
│   ├── Abbeville.json
│   ├── Aiken.json
│   ├── Allendale.json
│   ├── Anderson.json
│   ├── Bamberg.json
│   ├── Bamberg_Retabulated.json
│   ├── Barnwell.json
│   ├── Beaufort.json
│   ├── Berkeley.json
│   ├── Calhoun.json
│   ├── Charleston.json
│   └── Cherokee.json
├── 13_24.zip
│   ├── Chester.json
│   ├── Chesterfield.json
│   ├── Clarendon.json
│   ├── Colleton.json
│   ├── Darlington.json
│   ├── Dillon.json
│   ├── Dorchester.json
│   ├── Edgefield.json
│   ├── Fairfield.json
│   ├── Florence.json
│   ├── Georgetown.json
│   └── Greenville.json
├── 25_36.zip
│   ├── Greenwood.json
│   ├── Hampton.json
│   ├── Horry.json
│   ├── Jasper.json
│   ├── Kershaw.json
│   ├── Lancaster.json
│   ├── Laurens.json
│   ├── Lee.json
│   ├── Lexington.json
│   ├── Marion.json
│   ├── Marlboro.json
│   └── McCormick.json
└── 37_47.zip
    ├── Newberry.json
    ├── Oconee.json
    ├── Orangeburg.json
    ├── Pickens.json
    ├── Richland.json
    ├── Saluda.json
    ├── Spartanburg.json
    ├── Sumter.json
    ├── Union.json
    ├── Williamsburg.json
    └── York.json
```

## License

All data in this repository is sourced from public records provided by the [South Carolina State Election Commission](https://www.scvotes.org). Please consult [South Carolina Code of Laws Title 30 - Public Records](https://www.scstatehouse.gov/code/title30.php) for details on permissible use.

The commisssion [advises](https://www.scvotes.org/sale-voter-registration-lists):

>Obtaining or using public records for commercial solicitation directed to any person in this State is prohibited under South Carolina Code Section 30-2-50 .

>In addition, a person or private entity shall not knowingly obtain or use any "personal information" obtained from a public body for commercial solicitation directed to any person in the State. Section 30-2-50(A) . "Personal information" is defined as follows: Information that identifies or describes an individual including, but not limited to, an individual's photograph or digitized image, social security number, date of birth, driver's identification number, name, home address, home telephone number, medical or disability information, education level, financial status, bank account(s) number(s), account or identification number issued by and/or used by any federal or state governmental agency or private financial institution, employment history, height, weight, race, other physical details, signature, biometric identifiers, and any credit records or reports. Section 30-2-30(1).

>PENALTY: A person knowingly violating the provisions of 30-2-50(A) is guilty of a misdemeanor and, upon conviction, must be fined an amount not to exceed five hundred dollars or imprisoned for a term not to exceed one year, or both. Section 30-2-50(D) .

I am not a lawyer and cannot adivise on this matter.

## A Matt Hodges project

This project is maintained by [@hodgesmr](http://twitter.com/hodgesmr).

_Please use it for good, not evil._
