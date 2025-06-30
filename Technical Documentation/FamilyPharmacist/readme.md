
# **OPTION 1 = FLOW DIGITAL CONVENTION FAMILY PHARMACIST > FARMAFLUX FRONTEND**

From the pharmacy software, a link must be established to the PHM portal. On this PHM portal, two eForms will be available: one for vaccination and one for the “family pharmacist".

When the pharmacist navigates to the "family pharmacist" section, they will arrive at the mock-up page as shown in the ISV meeting. Here, digital signing can be activated by clicking the "Sign digitally" button in the signing block.

 ![image](https://github.com/user-attachments/assets/fe982160-df64-4014-8733-297b46be05e5)


Next, the eID will be requested, and Nitro will automatically initiate the eID read-out.
  -	Technical info eid via nitro (integration will be done by Farmaflux – no actions from ISV demanded)
    -	Hieronder een link naar de documentatie van onze iDentity hub:
      -	https://connectivegroup.my.site.com/s/article/Identity-Hub-Integration-Guide?language=en_US
    -	Scopes .beID:
      -	https://connectivegroup.my.site.com/s/article/IDS-1-5-Integration-Guide-Part-1?language=en_US#Scopes
  
  - In the backend, Nitro will read the data from the eID and send it to Farmaflux.
  - Farmaflux will then place the received information from the patient on the convention.
  - Farmaflux will also place the information from the CRM of the pharmacy and pharmacy holder onto the agreement.
  - Farmaflux sends the completed agreement with all data fields filled back to Nitro. Nitro adds a timestamp and seal, and returns the document to Farmaflux.

Farmaflux will archive the signed document and make it available on the PCDH so that it can be consulted via the HUB - METAHUB by the patient and their healthcare providers with a therapeutic relationship. 

The document will also be downloadable from the “family pharmacist” page in the digital signing section.
 ![image](https://github.com/user-attachments/assets/18fac066-0c88-43b8-9992-fdb7a0cb099b)

**Install of Nitro read-out software:**
https://connectivegroup.my.site.com/s/article/How-do-I-system-install-the-Connective-browser-package-Windows)
  - The first time Nitro initiates a digital read-out, the necessary program for Nitro’s read-out will be automatically installed if it is not already present.
  - Farmaflux can also provide a button in the eForm that allows the pharmacist to install the program manually at a desired moment.
  - A third option, involving a push installation of the required software, was not retained by the software vendors.

**In any case, the software vendors are not responsible for support regarding digital signing. This support will be provided by Farmaflux and Nitro.**


# **OPTION 2 = FLOW DIGITAL CONVENTION FAMILY PHARMACIST > ISV FRONTEND**

-	The pharmacist must be able to click a 'digitally sign' button.
  
-	Next, the system requests to insert the eID of the patient.
  
-	The reading out is started in the background
  
-	The following information is collected from the eID of the patient:
    -	[Lastname]
    -	[Firstnames]
    -	[Streetname and number]
    -	[Zipcode]
    -	[Location]
    -	[EidCardNumber]
    -	[CardValidityFrom]
    -	[CardValidityTo]
    -	[EidNationalNumber]
    -	[EidPhoto]

-	The following information of the pharmacy and pharmacy holder is collected in the software:
    -	[PharmacyHolderLastname]
    -	[PharmacyHolderfirstnames]
    -	[PharmacyHolderRIZIV]
    -	[PharmacyName]
    -	[PharmacyStreetName and number]
    -	[PharmacyZipcode]
    -	[PharmacyLocation]
    -	[PharmacyAPBNumber]

-	The information from the eID from the patient and the pharmacy and pharmacist information is placed on the corresponding fields of the convention.
    -	(NL) https://www.apb.be/nl-BE/files/F3BB5A61-0EB1-455F-A86D-3BFA2A6B501A.pdf?title=overeenkomst-huisapotheker
    -	(FR) https://www.apb.be/fr-BE/files/A0E8879B-2F8C-4EB3-8754-D24C39E90EB4.pdf?title=convention-pharmacien-de-reference

A version of the agreement will be made available in which the checkboxes are automatically marked, and the year and the fee for that year are filled in. Additionally, the informational flyer for the patient will also be included in the document.

  - **Fill in the patient data:**
	[Lastname],  [firstnames], [streetname and number] [zipcode] [Location]

  - **Fill in data from pharmacy and pharmacy titularis known in the system**
	[PharmacyHolderLastname],[PharmacyHolderfirstnames], [PharmacyHolderRIZIV] 
	[PharmacyName], [PharmacyStreetName and number] [PharmacyZipcode] [PharmacyLocation] [PharmacyAPBNumber]

  - **Fill in the data from the pharmacy:**
	[PharmacyLocation]

  - **Fill in the date:**
	[SessionDateTime]

  - **Fill in the signing information of the patient**
“Digitally signed by” 
	[Lastname],  [firstnames], [EidCardNumber], [CardValidityFrom], [CardValidityTo], [EidNationalNumber], [EidPhoto]

  - **Fill in the signing information of the pharmacy**
“Digitally signed by” 
	 [PharmacyHolderLastname],  [PharmacyHolderfirstnames]

-	The software vendor will create an eSeal with timestamp before sending the pdf-document to farmaflux. Below more information about the seal and timestamp from Nitro. We expect the same from the softwarevendors. We want proof that the eID readout has taken place.
  
    -	Timestamp Nitro
        -	All signatures placed via Nitro Sign Enterprise Verified include a timestamp from a certified Timestamp Authority (TSA). A timestamp shows the officially recorded date and time at which the individual electronic signature was made. As such, it forms part of the audit trail and provides evidence of the authenticity of the signature. Currently, Nitro Sign Enterprise Verified uses the Qualified TSAs provided by Certigna and GlobalSign.
   	
    -	Seal Nitro
        -	Nitro Sign Enterprise Verified can automatically sign or countersign documents using a company certificate as soon as the document or package is sent to the API and this signing method is specified. A company seal can be considered a co-signature by a legal entity, ensuring the integrity of the document (i.e., it has not been altered since it was sent by the issuer) and guaranteeing its origin (i.e., the document comes from the authentic source and no malicious party can impersonate the underlying entity).

-	Farmaflux will archive the signed document and make it available on the PCDH so that it can be consulted via the HUB - METAHUB by the patient and their healthcare providers with a therapeutic relationship. 
The document will also be downloadable in the software.

