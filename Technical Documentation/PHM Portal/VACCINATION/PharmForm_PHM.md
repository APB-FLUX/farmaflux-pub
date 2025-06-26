# Accessing the PHM Portal 

- [Accessing the PHM Portal](#accessing-the-phm-portal)
  - [Accessing the PHM Portal vaccination through the phm app](#accessing-the-phm-portal-vaccination-through-the-phm-app)
    - [CheatSheet questionnaire type ‘phm’](#cheatsheet-questionnaire-type-phm)
  - [Accessing the PHM Portal vaccination through the popvax app](#accessing-the-phm-portal-vaccination-through-the-popvax-app)
    - [CheatSheet questionnaire type ‘popvax’](#cheatsheet-questionnaire-type-popvax)
  - [Accessing the PHM Portal vaccination through the vaccinnetregistration app](#accessing-the-phm-portal-vaccination-through-the-vaccinnetregistration-app)
    - [CheatSheet questionnaire type ‘vaccinnetregistration’](#cheatsheet-questionnaire-type-vaccinnetregistration)

*See also [REST Services](https://apbcommunity.atlassian.net/wiki/spaces/FLUX/pages/105251339/Pharm+Forms+-+REST+Services)* 

## Accessing the PHM Portal vaccination through the phm app
### CheatSheet questionnaire type ‘phm’

1. ***Idppharmacysaml()***
1. listAppRepository?select=Patient
1. idppharmacylaunch(patient, language, ***‘checkpatient’***) if no patient with correct INSZ then launchaction will false
1. idppharmacylaunch (patient, language, ***phm***)
1. ***Launchaction: true*** ==> the launchaction will always return true permitting the pharmacist to acces the information of administered vaccins.



## Accessing the PHM Portal vaccination through the popvax app
### CheatSheet questionnaire type ‘popvax’

1. ***Idppharmacysaml()***
1. listAppRepository?select=Patient
1. idppharmacylaunch(patient, language, ***‘checkpatient’***) if no patient with correct INSZ then launchaction will false
1. idppharmacylaunch (patient, language, ***popvax***)
2. ***Launchaction: true*** ==> Patient is in TARGET GROUP to be sensibilised.


## Accessing the PHM Portal vaccination through the vaccinnetregistration app
### CheatSheet questionnaire type ‘vaccinnetregistration’

1. ***Idppharmacysaml()***
1. listAppRepository?select=Patient
1. idppharmacylaunch(patient, language, ***‘checkpatient’***) if no patient with correct INSZ then launchaction will false
1. idppharmacylaunch (patient, language, ***vaccinnetregistration***)
2. ***Launchaction: true*** ==> ==> the launchaction will always return true permitting the pharmacist to acces the information of administered vaccins.

