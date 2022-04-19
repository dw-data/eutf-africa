# Taking stock of the EU Emergency Trust Fund for Africa

Idea: [Gianna-Carina Grün](https://twitter.com/giannagruen)

Data analysis, visualization, research and writing: [Kira Schacht](https://twitter.com/daten_drang), [Gianna-Carina Grün](https://twitter.com/giannagruen)

Editing: Milan Gagnon

This project is a collaboration of several partners within the [European Data Journalism Network (EDJNet)](https://www.europeandatajournalism.eu/). While DW was project leads, [VoxEurop](https://voxeurop.eu/en/), [Openpolis](https://www.openpolis.it/) and [OBCT](https://www.balcanicaucaso.org/eng) were contributing partners.

This project consists of multiple stories published over consecutive days:
- DW: "How the EU spent billions to halt migration from Africa" evaluating whether the EUTF reached its goals –– *available in [English](https://dw.com/a-61362906), [Arabic](https://p.dw.com/p/49qAg) and [German](https://dw.com/a-61443980)*
- DW: "EU uses development aid to strongarm Africa on migration" placing the EUTF in context of European development aid efforts –– *available in [English](https://dw.com/a-61375189), [Arabic](https://p.dw.com/p/49uV7) and [German](https://dw.com/a-61430196)*
 - DW: "How Germany manages EU funds in Africa" outlining the role of Germany as the EUTF's biggest state donor –– *available in [English](https://dw.com/a-61375626), [Arabic](https://p.dw.com/p/49yN3) and [German](https://dw.com/a-61445516)*
- Openpolis: A cosa sono serviti i soldi dell’Eutf? [Italian](https://www.openpolis.it/a-cosa-sono-serviti-i-soldi-delleutf/)


## Data sources

### EUTF

The data compiled for this analysis can be found [here](https://docs.google.com/spreadsheets/d/11Z49kZy0Pdx5VX7viqsWtpP9wgwCIVxXFb1amvuOqEY/edit?usp=sharing). Source for the data found in this spreadsheet file is the European Comission. We started with their AVKO database that is used to document results from the EUTF projects. The script collecting the data from AVKO can be found [here](cleaning/). We consolidated the data from this database with the projects from the Fund's "all projects" page, the "projects by partner" and "projects by topic" page – since these did not match entirely – , as well as with data from previous years that we scraped from individual country pages since 2018. 

The AVKO database distinguishes between parent projects and also lists the child projects belonging to those parent projects and further lists contracts signed for the different projects. We based our analysis on the available data for parent projects and only included three child projects that were distinctively different from their parent projects. Thus, we arrived at a total project number of 253 projects.

### Frontex: Detected Irregular Border Crossings

Data for detected irregular border crossings were downloaded from the Frontex Website on February 8, 2022. The original file can be found in the [data](data/) folder.

### Eurostat: First-time asylum-applications

Data for first-time asylum-applications were downloaded from the Eurostat database (entry: migr_asyappctzm) on February 8, 2022. Until January 2020, we are looking at EU-28, including Britain, and from February 2020 referring with EU to the EU_27, excluding Britain. The original files can be found in the [data](data/) folder.

### UNHCR

Data for displaced people were downloaded from UNHCR on February 8, 2022. The original file can be found in the [data](data/) folder. For our analysis, we summed up all people of concern to UNHCR, including refugees, asylum-seekers, internally displaced people and stateless people originating from and residing in an African country.


### OECD: Official Development Aid

Data on official development aid is collected by the OECD Development Aid Committee (DAC). It can be accessed via the [OECD Data Portal](https://stats.oecd.org/), dataset **DAC3A**(“Aid (ODA) commitments to countries and regions”) or the [Query Qizard for International Development Statistics (QWIDS)](https://stats.oecd.org/qwids/).  The data used here refers to official development aid (ODA) commitments by donor and recipient, from 2011 to 2020. Data from 2020 are not complete yet at the time of publication.



## Data analysis

A large part of the data analysis is documented in the various tabs of [this Google Spreadsheet](https://docs.google.com/spreadsheets/d/1kERNIDXJe55Gt64fiNupRA5xTpzOlZt3Cg3amr-kcyQ/edit?usp=sharing). 


## Interviews

For this article series, we conducted several on-the-record interviews with the following experts (in alphabetical order):

* [Kwaku Arhim-Sam](https://www.thh-friedensau.de/mitarbeiter/kwaku-arhin-sam/), Head of Evaluation an Friedensau University and co-author of a [study on Ghana and EU migration policy](https://dgap.org/en/research/publications/ghana-eus-migration-partner)
* [Inken Bartels](https://www.imis.uni-osnabrueck.de/en/members_staff/imis_members/bartels_inken.html), migration researcher at the University of Osnabrück and author of a [Heinrich Böll study on the EUTF](https://www.boell.de/sites/default/files/money_against_migration.pdf)
* [Alia Fakhry](https://dgap.org/en/user/26724/alia-fakhry), migration researcher at the German Council on Foreign Relations and author of the [study "How to talk about migration in Africa"](https://dgap.org/en/research/publications/how-talk-about-migration-africa) 
* [David Kipp](https://www.swp-berlin.org/en/researcher/david-kipp), migration researcher at the [German Institute for International and Security Affairs](https://www.swp-berlin.org/en/),
* [Anna Knoll](https://ecdpm.org/people/annaknoll/), Head of the migration and mobility focus area at the think tank European Centre for Development Policy Management (ECDPM)  and co-author of a commentary on ["Why migration and mobility should – but probably won’t – be at the heart of the EU-AU Summit"](https://ecdpm.org/talking-points/why-migration-mobility-should-probably-wont-be-heart-eu-au-summit/)
* [Sara Lorenzini](https://webapps.unitn.it/du/en/Persona/PER0000845/Pubblicazioni), Professor of Modern History at the [School of International Studies](https://webapps.unitn.it/du/en/StrutturaAccademica/STO0008633/Persone) and at the Department of Humanities of the University of Trento
* [Ottilia Anna Maunganidze](https://afripoli.org/profile/ottilia-anna-maunganidze), Head of Special Projects in the Office of the Executive Director at the [Institute for Security Studies (ISS)](https://issafrica.org/author/ottilia-anna-maunganidze) and author of a policy brief on [Africa Europe migration](http://issafrica.s3.amazonaws.com/site/uploads/PB-166.pdf)
* [Jan Orbie](https://www.ugent.be/ps/politiekewetenschappen/gies/en/team/professors/jan-orbie), director of the [Centre for EU Studies at Ghent University](https://www.ugent.be/ps/politiekewetenschappen/gies/en)

Additional interviews were conducted by collaborating partners [VoxEurop](https://voxeurop.eu/en/), [Openpolis](https://www.openpolis.it/) and [OBCT](https://www.balcanicaucaso.org/eng)


We also contacted the Commission asking for clarification on 15 questions regarding the data presented on the EUTF's website - after we noticed some inconsistencies - and the EC's assessment of the EUTF. The response did not arrive in time to be incorporated to significant extent in our reporting. A selection of relevant questions and answers can be found in the [documents](documents/) folder.

## Documents

In our reporting, we quote several studies and EU documents. To be able to reference them even if they were taken offline, we collected them in the [documents](documents/) folder.
