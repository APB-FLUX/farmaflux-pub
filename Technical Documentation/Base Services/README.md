# Assurpharma Technical Documentation

## Integration Specification 

* [doc] [ASSURPHARMA Integration Specification v2.3.1](<Assurpharma/ASSURPHARMA - Integration Specifications/ASSURPHARMA_IntegrationSpecification_v2.3.1.docx>)
* [pdf]


## Overview of the referenced data and their compatibility.  
### Single Message

- Abbreviation	SMC
- Version	2.0.5 (:information_source: *test on SMC 2.0.6 still to be done but should work* )
- Source: [FARMAFLUX - SMC Specifications](<Assurpharma/FARMAFLUX - SMC Specifications>)


### Pharmacy SDK 
- Abbreviation	SDK
- Source
  - ftp.apb.be 
  - user: anonymous pwd: /
  - subfolder /SDK

### Application Design
- Abbreviation	ASSURPHARMA AD
- Source: [ASSURPHARMA - Application Design](<Assurpharma/ASSURPHARMA - Application Design>)


### BVAC Document message formats
- Abbreviation	BVAC Document Format
- Source:	[Bijlage 3 - Panoramix - message format3 - update 2023](<Assurpharma/ASSURPHARMA - BVAC xml/Bijlage 3 - Panoramix - message format3 - update 2023.xlsx>)


### AssurPharma Webservices Specification for insurers
- Abbreviation	WSDl Insurer
- Source
  - [Acceptance]
    - Online:  https://acc-tip.gfd-dpp.be/be-apb-gfddpp-services-TIPSystem/ASSURPHARMATIPSystemServices?wsdl
    - WSDL  
..\ASSURPHARMA - Webservices Specifications
    - Xsd of the webservice (..\ASSURPHARMA - xsd\PanoramixTIPSystemServices_protocol-1_0.xsd)
    - Xsd of the encrypted part of the request parameters. (..\ASSURPHARMA - xsd\assuralia-request-parameters-v20130916.xsd
  - [Production]  The following messages are supported:  [portType][Operation][input][output]
    - [PanoramixTIPSystemServices] [getBvacData] [getBvacData] [getBvacDataResponse]
    - [PanoramixTIPSystemServices] [checkAlive] [checkAlive] [checkAliveResponse]

### AssurPharma CBFA Configuration
 - Abbreviation:	CBFA Configuration
    - Source: [xsd](<Assurpharma/ASSURPHARMA - xsd/assurharma-bvac-configuration.xsd>)

Per party involved in Panoramix we have an <insurer> entry
-	In the \<insurer> entry, 
    - we always have a \<name>
    - we always have an \<end-point-type> which indicates HTTPS or SFTP.  Please mind that for a transporter this indicates the method he can use to come and get the BVAC’s, but that where the BVAC’s are put (be it queue or SFTP directory) are decided by the endpoint type of the insurer for which the messages are meant
-	in the case of an end-insurer, 
    - we have a \<CBFA>
    - we have a \<encryption-key> which points to the location of the public key that will be used to encrypt the certiciates
    - we can have the entry \<party> for all parties able to access its data (i.e. the transporter). There we have 
        -	The \<name> of the party allowed to do the transport
        -	The \<requestor-id> of the party allowed to do the transport
-	in the case of a transporter, 
    -	we have a \<requestor-id>
        -	This id exists because a party doing transport doesn’t necessarily have a CBFA number. E.g. in the case of Assurcard. 
        -	If transport by web service, this id needs to be communicated to the party wanting to do the transport since they will need to specify it in their request
        -	Guidance is to use the CBFA number as requestor id if the party does have one, and if not, use the name of the part in capital letters (e.g. ASSURCARD)
    -	we have a \<transport-key> which points to the location of the public certificate of the party doing the transport 
	

### 12.7	Assuralia Identification  Insurers 
- Abbreviation:	Assuralia Identification Insurer
- Source	
  - [Full] [Assuralia Identificatie verzekeraars CBFA Panoramix - technical registration parameters - 13-09-2013.xlsx](<Assurpharma/ASSURPHARMA - BVAC xml/Assuralia Identificatie verzekeraars CBFA Panoramix - technical registration parameters - 13-09-2013.xlsx>) (:information_source: *updated list of insurers to be supplied* )
  - [Pilot] [Assuralia Identification Insurers - Pilot](<Assurpharma/ASSURPHARMA - BVAC xml/Assuralia Identification Insurers - Pilot.xlsx>)


### 12.8	TIP System Services
- Abbreviation:	TIP System Services
- Source	
  - [xsd] [system-services.xsd](<Assurpharma/ASSURPHARMA - xsd/system-services.xsd>)
  - [xml] [system-services-sample.xml](<Assurpharma/ASSURPHARMA - xsd/system-services-sample.xml>)


### 12.9	GetBVAC WebService Error Messages
- Abbreviation:	GetBVAC Webservice Error Messages
- Source	
  - [excell] [Assuralia TIP-Insurer Webservice Error Messages - Pilot.xlsx](<Assurpharma/ASSURPHARMA - BVAC xml/Assuralia TIP-Insurer Webservice Error Messages - Pilot.xlsx>)