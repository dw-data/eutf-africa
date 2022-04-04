# EUTF for Africa: Data cleaning

**Script by:** [Kira Schacht](https://www.twitter.com/daten_drang)

# Files

| Name                       | Content                                                                |
|----------------------------|------------------------------------------------------------------------|
| `cleaning/eutf_scrape.Rmd` | The main R markdown script. Run in RStudio to reproduce this analysis. |
| `cleaning/data.RData`      | The R Data file containing the finished datasets.                      |
| `data/...`                 | Data files                                                             |

# Data source

The data on EUTF projects comes from the AKVO monitoring platform. A
full XML file of all projects linked to the EUTF is available
[here](https://eutf.akvoapp.org/en/organisation/3394/).

The version used for this analysis was last updated on 17. December
2021.

# Create datasets

Here is a step-by-step-explanation of the code we used to create our
analysis data sets. You can explore it yourself by opening
`eutf_scrape.Rmd` in RStudio.

## Read data

Read raw XML data from file `akvo-20211217-130832.xml`

## Project info dataset

For every project (XML node `iati-activity`), create one row containing:

-   IATI project ID
-   project title
-   project summary
-   partner organizations
    -   funding partners (in XML: `role=1`)
    -   accountable partners (in XML: `role=2`)
    -   extending partners (in XML: `role=3`)
    -   implementing partners (in XML: `role=4`)
-   project start and end dates (in XML: `activity-date type='2'` and
    `type='3'`)
-   project budget
-   recipient country or countries
-   project location
-   project topics according to the 4 thematic fields of the EUTF:
    1.  Greater economic and employment opportunities
    2.  Strengthening resilience
    3.  Improved migration management
    4.  Improved governance and conflict prevention
-   OECD development aid CRS purpose codes
-   URLS of linked documents
-   related activities: parent projects, child projects, sibling
    projects

| iati_id                                    | prefix | title                                                                                                                      | partner_implementing                                                                                                                       | date_start | date_end   |     budget | recipient_country                                                                      |
|:-------------------------------------------|:-------|:---------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------|:-----------|:-----------|-----------:|:---------------------------------------------------------------------------------------|
| EU Trust Fund for Africa Results Framework | NA     | EU Trust Fund for Africa Results Framework                                                                                 | NA                                                                                                                                         | NA         | NA         | 4600000000 | BF, CI, CM, LY                                                                         |
| T05-EUTF-HOA-REG-36                        | DEC    | IGAD Promoting Peace and Stability in the Horn of Africa Region (IPPSHAR)                                                  | Austrian Development Agency, Intergovernmental Authority on Development                                                                    | NA         | 2024-06-30 |  361440000 | UG, DJ, ER, ET, KE, SD, SO, SS, TZ                                                     |
| T05-EUTF-SAH-REG-18                        | DEC    | Programme d’urgence pour la stabilisation des espaces frontaliers du G5 Sahel (PDU)                                        | GIZ, Luxembourg Development Cooperation Agency, Centre pour le dialogue humanitaire - HD, Agence Française de Développement                | NA         | 2022-11-19 |  144479592 | BF, ML, MR, NE, TD                                                                     |
| T05-EUTF-SAH-REG-16                        | DEC    | Protection and sustainable solutions for migrants and refugees along the Central Mediterranean route                       | International Organization for Migration, United Nations High Commissioner for Refugees                                                    | NA         | 2020-12-01 |  125000000 | BF, CI, CM, GH, GM, GN, GW, ML, MR, NE, NG, SN, TD                                     |
| T05-EUTF-REG-REG-04                        | DEC    | Protection and sustainable solutions for migrants and refugees along the Central Mediterranean route                       | International Organization for Migration, United Nations High Commissioner for Refugees                                                    | 2017-12-01 | 2020-12-01 |  115000000 | BF, CI, CM, DJ, ER, ET, GH, GM, GN, KE, LY, ML, MR, NE, NG, SD, SN, SO, SS, TD, TZ, UG |
| T05-EUTF-HOA-SO-59                         | DEC    | Somalia State Building and Resilience Contract                                                                             | NA                                                                                                                                         | NA         | NA         |  107400000 | SO                                                                                     |
| T05-EUTF-NOA-MA-07                         | DEC    | Appui aux actions des autorités marocaines contre les réseaux facilitant les flux migratoires irréguliers                  | NA                                                                                                                                         | 2019-12-10 | 2021-09-30 |  101750000 | MA                                                                                     |
| T05-EUTF-HOA-SO-59-02                      | CTR    | Somalia State and Resilience Building Contract                                                                             | NA                                                                                                                                         | NA         | 2021-10-15 |   99400000 | SO                                                                                     |
| T05-EUTF-HOA-SO-57                         | DEC    | Inclusive Local and Economic Development - ILED                                                                            | NA                                                                                                                                         | 2018-05-29 | NA         |   98200000 | SO                                                                                     |
| T05-EUTF-NOA-LY-03                         | DEC    | Managing mixed migration flows in Libya through expanding protection space and supporting local socio-economic development | United Nations Development Programme, United Nations High Commissioner for Refugees, UNICEF, International Organization for Migration, GIZ | 2017-04-12 | NA         |   90000000 | LY                                                                                     |

## Results list

For every project, create one row for every result indicator containing:

-   IATI project ID
-   result type: Reporting category of results,
    e.g. `EUTF Common Output Indicators`
-   title of indicator
-   reporting period start and end dates
-   target value
-   actual value

| iati_id                | result_type     | title                                                                                                                                                                                                                        | period_start | period_end | target | actual  |
|:-----------------------|:----------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|:-----------|:-------|:--------|
| T05-EUTF-NOA-REG-14-01 | EUTF indicators | Number of jobs created                                                                                                                                                                                                       | 2015-01-01   | 2025-12-31 |        |         |
| T05-EUTF-NOA-REG-14-01 | EUTF indicators | Number of projects by diaspora members                                                                                                                                                                                       | 2015-01-01   | 2025-12-31 |        |         |
| T05-EUTF-NOA-REG-14-01 | EUTF indicators | Number of migrants in transit and forcibly displaced people protected or assisted                                                                                                                                            | 2015-01-01   | 2025-12-31 |        | 3794.00 |
| T05-EUTF-NOA-REG-14-01 | EUTF indicators | Number of migrants, or potential migrants, reached out by information campaign on migration and risks linked to irregular migration                                                                                          | 2015-01-01   | 2025-12-31 |        |         |
| T05-EUTF-NOA-REG-14-01 | EUTF indicators | Number of voluntary returns or humanitarian repatriation supported                                                                                                                                                           | 2015-01-01   | 2025-12-31 |        |         |
| T05-EUTF-NOA-REG-14-01 | EUTF indicators | Number of returning migrants benefiting from reintegration assistance                                                                                                                                                        | 2015-01-01   | 2025-12-31 |        |         |
| T05-EUTF-NOA-REG-14-01 | EUTF indicators | Number of Institutions (National and local) and Non-State actors directly supported through capacity building on migration management                                                                                        | 2015-01-01   | 2025-12-31 |        |         |
| T05-EUTF-NOA-REG-14-01 | EUTF indicators | Number of border stations supported to strengthen border control                                                                                                                                                             | 2015-01-01   | 2025-12-31 |        |         |
| T05-EUTF-NOA-REG-14-01 | EUTF indicators | Number of staff from governmental institutions, internal security forces and relevant non-state actors trained on security, border management, CVE, conflict prevention, protection of civilian populations and human rights | 2015-01-01   | 2025-12-31 |        |         |
| T05-EUTF-NOA-REG-14-01 | EUTF indicators | Number of people participating in conflict prevention and peace building activities                                                                                                                                          | 2015-01-01   | 2025-12-31 |        |         |

## Partner organizations list

Create a list of every partner organization witht he following
information:

-   name
-   AKVO type: a numerical value describing the type of organization
-   the number of occurrences in each role:
    -   funding partner (in XML: `role=1`)
    -   accountable partner (in XML: `role=2`)
    -   extending partner (in XML: `role=3`)
    -   implementing partner (in XML: `role=4`)

<!-- -->

    ## `summarise()` has grouped output by 'name', 'type'. You can override using the `.groups` argument.

| name                                                     | type | funding | accountable | extending | implementing |
|:---------------------------------------------------------|:-----|--------:|------------:|----------:|-------------:|
| International Organization for Migration                 | 21   |       0 |           0 |         0 |           51 |
| GIZ                                                      | 10   |       0 |           0 |         0 |           47 |
| United Nations High Commissioner for Refugees            | 21   |      13 |           1 |         0 |           36 |
| Agence Française de Développement                        | 10   |       8 |           0 |         0 |           23 |
| ENABEL - Belgian Development Agency                      | 10   |       0 |           0 |         0 |           23 |
| UNICEF                                                   | 22   |       4 |           0 |         0 |           22 |
| United Nations Development Programme                     | 40   |       1 |           0 |         0 |           19 |
| Spanish Agency for International Development Cooperation | 10   |       1 |           0 |         0 |           18 |
| Civipol                                                  | 40   |       0 |           0 |         0 |           16 |
| World Food Programme                                     | 40   |       4 |           0 |         0 |           15 |

## Recipient country list

For every project, list recipient countries and, if available, the
`percentage` attributed to them, as follows:

-   IATI project ID
-   project budget
-   ISO alpha-2 country code of recipient country
-   percentage attributed to recipient country

This can be used to estimate the budget share of regional projects
attributable to each recipient country.

| iati_id                |     budget | recipient_country | recipient_percentage |
|:-----------------------|-----------:|:------------------|:---------------------|
| T05-EUTF-SAH-TD-07-03  |  1000000.0 | TD                | NA                   |
| T05-EUTF-SAH-TD-07-02  |  7000000.0 | TD                | NA                   |
| T05-EUTF-SAH-TD-01-11  |  1172327.0 | TD                | NA                   |
| T05-Eutf-SAH-TD-01-10  |   892000.0 | TD                | NA                   |
| T05-EUTF-SAH-TD-01-09  |   947492.8 | TD                | NA                   |
| T05-EUTF-SAH-TD-08-01  | 10000000.0 | TD                | NA                   |
| T05-EUTF-SAH-REG-20-01 |  9998500.0 | BF                | NA                   |
| T05-EUTF-SAH-REG-20-01 |  9998500.0 | ML                | NA                   |
| T05-EUTF-SAH-REG-20-01 |  9998500.0 | MR                | NA                   |
| T05-EUTF-SAH-REG-20-01 |  9998500.0 | NE                | NA                   |

## List of discontinued projects

To find projects that might have been discontinued, we search for
projects referred to as “related activities” in the database that don’t
have their own separate entry.

1.  list all IATI IDs in separate `iati-activity`entries
2.  list all IATI IDs referred to in `related-activity`tags
3.  list which entries of 2. don’t appear in 1.

<!-- -->

    ## [1] ", , ,  T05-EUTF-HOA-SO-46.3 & T05-EUTF-HOA-SO-03.06 & T05-EUTF-HOA-SO-57.03, an African-European TVET initiative, Assistance et protection des migrants les plus vulnérables en Afrique de l’Ouest, T05-EUTF, T05-EUTF-HOA-57-07, T05-EUTF-HOA-ER-100, T05-EUTF-HOA-ER-101, T05-EUTF-HOA-ER-102, T05-EUTF-HOA-ER-87, T05-EUTF-HOA-ER-92, T05-EUTF-HOA-ER-99, T05-EUTF-HOA-ET-42-03, T05-EUTF-HoA-REG-26-05, T05-EUTF-HOA-REG-71-01, T05-EUTF-HOA-SD, T05-EUTF-HOA-SO-57-03, T05-EUTF-HOA-SO-57-04, T05-EUTF-HOA-SO-57-05, T05-EUTF-HOA-SS-50-01, T05-EUTF-HOA-SS-50-03, T05-EUTF-HOA-SS-93-01, T05-EUTF-NOA-, T05-EUTF-NOA-08-01, T05-EUTF-NOA-EG-01-03, T05-EUTF-NOA-EG-01-05, T05-EUTF-NOA-LY-07-02, T05-EUTF-NOA-MA-03-03, T05-EUTF-NOA-REG-01-02, T05-EUTF-NOA-REG-05-02, T05-EUTF-NOA-REG-08-02, T05-EUTF-SAH-BF-08-04, T05-EUTF-SAH-BF-08-07, T05-EUTF-SAH-MR-06-01, T05-EUTF-SAH-MR-06-02, T05-EUTF-SAH-NE-15, T05-EUTF-SAH-NG-05, T05-EUTF-SAH-NG-08, T05-EUTF-SAH-REG-21-01, T05-EUTF-SAH-SN-02-01, T05-EUTF-SAH-SN-06-04, XI-IATI-EC"
