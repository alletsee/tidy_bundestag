tidy\_bundestag
================

This repository contains R code to create tidy datasets for the German Bundestag election results.

The original data is provided by the [Federal Returning Officer (Bundeswahlleiter)](https://www.bundeswahlleiter.de/). The concept of tidy data is explained by Hadley Wickham [in his article "Tidy Data"](https://www.jstatsoft.org/article/view/v059i10/v59i10.pdf) in the *Journal of Statistical Software* (2014, Vol. 59, Issue 10).

Note that this is currently work in progress: I started with the 1949 Bundestag elections and will slowly work towards more recent elections. This project has been inspired by similar projects from [Arndt Leininger](https://gitlab.com/arndtl/tidy_kerg) and [Marie-Louise Timcke](https://interaktiv.morgenpost.de/analyse-bundestagswahl-2017/data/btw17_analysis.html) who both focused on the 2017 elections.

Folders and Files
-----------------

The folder **`code`** contains the R code to transform the un-tidy raw data into tidy data. The file names refer to the election years: `tidy_1949.r` refers to the 1949 Bundestag elections.

The original data as provided on the website of the Federal Returning Officer can be found in the folder **`data_raw`**. The resulting tidy datasets that are created when running the R code are stored in the folder **`data_tidy`**.

Variable Structure
------------------

The R code creates two different files for each election: `..._districts` includes district-level results, whereas `..._states` shows results for the states (Länder) and for the federal level.

Each row in the tidy dataset shows the election results for one party in one electoral district in one election for one type of vote ("Erststimme", "Zweitstimme"). The tidy datasets have the following variable structure:

-   `district_no`: number of the electoral district
-   `district_name`: name of the electoral district
-   `state`: name of the state to which the electoral district belongs (for results on state level: abbreviated name of the state)
-   `party_short`: abbreviated party name
-   `party_long`: full party name
-   `vote_type`: "Erststimme", "Zweitstimme"
-   `year`: year of election
-   `votes_party_district`: absolute number of votes for the respective party in the electoral district
-   `voteshare_party_district`: vote share for the respective party in the electoral district, in %
-   `voters_district`: total number of voters in the respective electoral district (both valid and invalid votes)
-   `validvotes_district`: valid votes for all parties in the respective electoral district
-   `invalidvotes_district`: invalid votes in the respective electoral district
-   `eligible_district`: absolute number of eligible voters in the respective district
-   `turnout_district`: voter turnout in the electoral district, in %

Original Data
-------------

The Federal Returning Officer provides a PDF file with an overview of all Bundestag elections: [Ergebnisse früherer Bundestagswahlen](https://bundeswahlleiter.de/dam/jcr/397735e3-0585-46f6-a0b5-2c60c5b83de6/btw_ab49_gesamt.pdf).

Moreover, there are separate websites with the results for each election as well the possibility to download the raw data:

-   1949 Bundestag elections: [website](https://bundeswahlleiter.de/bundestagswahlen/1949.html), [raw csv data](https://bundeswahlleiter.de/dam/jcr/d1ffdb9b-3d79-45a3-8e25-6a867c34d202/btw49_kerg.csv)
-   1953 Bundestag elections: [website](https://www.bundeswahlleiter.de/bundestagswahlen/1953.html), [raw csv data](https://www.bundeswahlleiter.de/dam/jcr/44e3b6bb-dfd4-4474-a9e5-7d57b507339e/btw53_kerg.csv)
-   1957 Bundestag elections: [website](https://www.bundeswahlleiter.de/bundestagswahlen/1957.html), [raw csv data](https://www.bundeswahlleiter.de/dam/jcr/6410974f-692e-466c-9fcb-98b1428cc73f/btw57_kerg.csv)
-   1961 Bundestag elections: [website](https://www.bundeswahlleiter.de/bundestagswahlen/1961.html), [raw csv data](https://www.bundeswahlleiter.de/dam/jcr/31655810-7fd3-46bd-827c-98e0fd39661f/btw61_kerg.csv)
-   1965 Bundestag elections: [website](https://www.bundeswahlleiter.de/bundestagswahlen/1965.html), [raw csv data](https://www.bundeswahlleiter.de/dam/jcr/326bd367-22d9-4a81-9800-1e159460a6f0/btw65_kerg.csv)
-   1969 Bundestag elections: [website](https://www.bundeswahlleiter.de/bundestagswahlen/1969.html), [raw csv data](https://www.bundeswahlleiter.de/dam/jcr/a372364b-236e-430f-855c-8014ea17700f/btw69_kerg.csv)
-   1972 Bundestag elections: [website](https://www.bundeswahlleiter.de/bundestagswahlen/1972.html), [raw csv data](https://www.bundeswahlleiter.de/dam/jcr/9b3b215a-2f4e-42b5-9abe-1f8b73e6717a/btw72_kerg.csv)
-   1976 Bundestag elections: [website](https://www.bundeswahlleiter.de/bundestagswahlen/1976.html), [raw csv data](https://www.bundeswahlleiter.de/dam/jcr/eb10180e-d751-4827-8e12-94818bd0992c/btw76_kerg.csv)
-   *(some elections are still missing here)*
-   2005 Bundestag elections: [website](https://www.bundeswahlleiter.de/bundestagswahlen/2005.html), [raw csv data](https://www.bundeswahlleiter.de/dam/jcr/01e65a67-6d5b-47ee-b8ec-0fd243493ebc/btw05_kerg.csv)
