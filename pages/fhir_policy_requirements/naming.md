---
title: Naming
keywords: naming
tags: [naming]
sidebar: overview_sidebar
permalink: naming.html
summary: Naming conventions for nationally defined FHIR assets
---

In order to promote consistency and make it easier for implementers to locate suitable profiles, extensions, value sets, etc, for their projects, a naming strategy will be adopted for nationally defined FHIR assets. The scope of this document is FHIR STU3.

For detailed definitions of concepts discussed within this guidance document, refer to the appropriate published version of the [FHIR standard](https://www.hl7.org/fhir/).


{% include requirement_box.html
	heading="FHIR-NAME-01: NHS Digital FHIR Profile name MUST follow an agreed format"
	content="This section details a set of rules that MUST be followed when creating NHS Digital FHIR profiles. The name of an NHS Digital profile consists of a number of name segments, and will be in the form:-

**[Base]-[BusinessName1]-[BusinessName2]-[FHIRAssetName]-[Version]**

The segments are defined as follows:-

- **Base**: The base profile, if one is used e.g. for a derived profile. This is therefore optional, but mandatory for CareConnect derived profiles.
- **BusinessName1**: The first business name of the profile, which could be a full name or an acronym related to the domain or project name e.g. ITK (Interoperability Toolkit), SPINE. The name MUST have at least one BusinessName segment. Where an asset may be used across several domains, business names SHOULD reflect that.
- **BusinessName2**: The second business name of the profile. The asset name MAY have a second BusinessName segment. Where there is a second business name, each BusinessName MUST be separated by a hyphen (-) character e.g. 'ADW-Accept'.
- **FHIRAssetName**: The name of the base FHIR asset. Mandatory
- **Version**: This is the major version number of the profile e.g. 'CareConnect-ITK-Encounter-1'. Mandatory

This name MUST be used in three places:

- The profile's **filename**.
- The **name** of the profile - specifically the name.value element in the StructureDefinition
- The profile's **logical ID**.

The logical ID forms the final segment of the URL of the StructureDefinition resource and is used to populate its logical id (e.g. the StructureDefinition.id element) when published on the a national FHIR Reference server. An example URL for a CareConnect derived profile (STU3) would be https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-Encounter-1, CareConnect-ITK-Encounter-1 being the value of the logical id and the profile's name.
"
%}

{% include requirement_box.html
	heading="FHIR-NAME-02: NHS Digital FHIR CodeSystem names MUST follow an agreed format"
	content="This section details a set of rules that MUST be followed when creating NHS Digital FHIR CodeSystems. The filename of the CodeSystem consists of a number of name segments and will be in the form:-

**[FHIRAssetName]-[BusinessName1]-[BusinessName2]-[Version]**

The segments are defined as follows:-

- **FHIRAssetName**: The name of the base FHIR asset e.g. CodeSystem. Mandatory
- **BusinessName1**: The first business name of the CodeSystem. The CodeSystem name MUST have at least one BusinessName segment,  e.g. 'CareConnect', 'ITK', 'SPINE'. Where a CodeSystem may be used across several domains, business names should reflect that.
- **BusinessName2**: The second business name of the CodeSystem. The CodeSystem MAY have a second BusinessName segment. Where there is a second BusinessName, each one MUST be separated by a hyphen (-) character. For example 'CodeSystem-SPINE-ErrorOrWarningCode'.
- **Version**: This is the major version number of the CodeSystem e.g. 'CodeSystem-ITK-CareSettingType-1'. Mandatory

This name MUST be used as the CodeSystems's filename.

In addition, The **[BusinessName1]-[BusinessName2]-[Version]** section of the CodeSystem's name MUST be used in two places:

- The **name** of the resource - specifically the name.value element
- The resource's **logical ID**

The logical ID forms the final segment of the URL of the CodeSystem resource and is used to populate its logical id (i.e. the CodeSystem.id element) when published on the a national FHIR Reference server. An example URL for a CodeSystem on the NHS Digital FHIR Reference Server is https://fhir.nhs.uk/STU3/CodeSystem/ITK-CareSettingType-1, ITK-CareSettingType-1 being the value of the logical id.
"
%}

{% include requirement_box.html
	heading="FHIR-NAME-03: NHS Digital FHIR ValueSet names MUST follow an agreed format"
	content="This section details a set of rules that MUST be followed when creating NHS Digital FHIR ValueSets. The filename of the ValueSet consists of a number of name segments and will be in the form:-

**[FHIRAssetName]-[BusinessName1]-[BusinessName2]-[Version]**

The segments are defined as follows:-

- **FHIRAssetName**: The name of the base FHIR asset e.g. ValueSet. Mandatory
- **BusinessName1**: The first business name of the ValueSet. The ValueSet name MUST have at least one BusinessName segment,  e.g. 'ITK', 'SPINE'. Where a ValueSet may be used across several domains, business names should reflect that.
- **BusinessName2**: The second business name of the ValueSet. The ValueSet MAY have a second BusinessName segment. Where there is a second BusinessName, each one MUST be separated by a hyphen (-) character e.g. 'ITK-PatientAllergyChangeType'.
- **Version**: This is the major version number of the ValueSet e.g. 'ValueSet-CareConnect-MedicationDosageMethod-1'. Mandatory

This name MUST be used as the ValueSet's filename.

In addition, The **[BusinessName1]-[BusinessName2]-[Version]** section of the ValueSet's name MUST be used in two places:

- The **name** of the profile - specifically the name.value element
- The resource's **logical ID**.

The logical ID forms the final segment of the URL of the ValueSet resource and is used to populate its logical id (i.e. the ValueSet.id element) when published on the a national FHIR Reference server. An example URL for a ValueSet on the NHS Digital FHIR Reference Server is https://fhir.nhs.uk/STU3/ValueSet/CareConnect-MedicationDosageRoute-1, CareConnect-MedicationDosageRoute-1 being the value of the logical id.
"
%}

{% include requirement_box.html
	heading="FHIR-NAME-04: FHIR Extension names MUST follow an agreed format"
	content="The name of the extension consists of a number of name segments and will be in the form:-

**[FHIRAssetName]-[Base]-[BusinessName1]-[BusinessName2]-[Version]**

The segments are defined as follows:-

- **FHIRAssetName**: The name of the base FHIR asset e.g. Extension. Mandatory
- **Base**: The base extension, if one is used e.g. for a derived CareConnect extension. This is therefore optional, but mandatory for CareConnect derived extensions.
- **BusinessName1**: The first business name of the extension. The asset name MUST have at least one BusinessName segment e.g. 'ITK', 'SPINE' etc. Where an asset may be used across several domains, business names should reflect that.
- **BusinessName2**: The second business name of the extension. The asset name MAY have a second BusinessName segment. Where there is a second business name, each one MUST be separated by a hyphen (-) character e.g. 'Extension-ITK-Informant-1'.
- **Version**: This is the major version number of the extension e.g. Extension-CareConnect-ConditionEpisode-1. Mandatory

This name MUST be used in three places:

- The extension's **filename**.
- The **name** of the extension - specifically the name.value element in the StructureDefinition
- The resource's **logical ID**.

The logical ID forms the final segment of the URL of the StructureDefinition resource and is used to populate its logical id (e.g. the StructureDefinition.id element) when published on the a national FHIR Reference server. An example URL for a CareConnect derived extension (STU3) is https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-AllergyCertainty-1, Extension-CareConnect-GPC-AllergyCertainty-1 being the value of the logical id.
"
%}

{% include requirement_box.html
	heading="FHIR-NAME-05: FHIR OperationDefinition names MUST follow an agreed format"
	content="The name of the OperationDefinition will be named using the following segment name format:

**[Base]-[BusinessName]-[OperationAction]-[OperationDefinitionKind]-[Version]**

The segments are defined to as follows:

- **Base**: The base OperationDefinition, if one is used. Optional but mandatory for CareConnect derived OperationDefinitions.
- **BusinessName**: A business name for the OperationDefinition. Optional.
- **OperationAction**: This could include a verb as the first part of the name.  An example would be ‘BookAppointment’.
- **OperationDefinitionKind**: Choice of 'Operation' or 'Query' fixed character strings. Mandatory.
- **Version**: This is the major version number of the OperationDefinition e.g. GPConnect-CareRecord-Operation-1. Mandatory.

This name MUST be used in three places:

- The OperationDefinition's **filename**.
- The **name** of the resource - specifically the name.value element in the OperationDefinition
- The resource's **logical ID**.

The logical ID forms the final segment of the URL of the OperationDefinition resource and is used to populate its logical id (e.g. the OperationDefinition.id element) when published on the a national FHIR Reference server. An example URL for an OperationDefinition (STU3) would be https://fhir.nhs.uk/STU3/OperationDefinition/GPConnect-RegisterPatient-Operation-1, GPConnect-RegisterPatient-Operation-1 being the value of the logical id.
"
%}

{% include requirement_box.html
	heading="FHIR-NAME-06: FHIR identifier systems MUST follow an agreed format"
	content="NHS Digital identifier systems may be used in the system element of the Identifier datatype. They establish the namespace for an asset's identifier.value element and have a URI datatype. This section details a set of rules that MUST be followed when creating NHS Digital FHIR identifier systems. The name of the identifier system consists of a number of name segments and will be in the form:-

**[Base URL]-[Id]-[BusinessName1]-[BusinessName2]-[BusinessName3]-[BusinessName4]**

The segments are defined as follows:-

- **Base URL**: The base URL, which will be in the format https://fhir.nhs.uk/. This is Mandatory.
- **Id**: The Id section of the identifier is formatted as a string 'Id'. This segment denotes that the string is an identifier system and is mandatory.
- **BusinessNames**: The business name segments describe the identifier system. The first business name is mandatory, but all subsequent ones are optional. There may be up to four business names each separated by a hyphen (-) character e.g. 'https://fhir.nhs.uk/Id/nhs-number', https://fhir.nhs.uk/Id/sds-role-profile-id.
"
%}

{% include requirement_box.html
	heading="FHIR-NAME-07: General naming conventions MUST also be followed"
	content="The following additional rules MUST also be adhered to for naming NHS Digital FHIR assets:-

- Rule 001: NHS Digital FHIR asset name segments MUST be human understandable. This means that the name must give a clear indication of the purpose or usage of the asset.
- Rule 002: NHS Digital FHIR asset names MUST follow the [Pascal Case capitalization] convention and MUST be in alphanumeric format only. In the [Pascal Case capitalization] convention, the first letter in each segment name and of each subsequent compound word must be capitalised e.g. BackColor.
- Rule 003: To improve the readability of long NHS Digital FHIR asset names, each string segment used to build an NHS Digital FHIR asset name, MUST be separated using the hyphen (-) character. For example :- Base-BusinessName1-BusinessName2-FHIRAssetName-VersionOfProfile or Base-BusinessName1-FHIRAssetName-VersionOfProfile
- Rule 004: CRUD function names MUST NOT be used in NHS Digital FHIR asset names. These are Create, Read, Update and Delete. Other variations should be avoided e.g. Retrieve, Modify, Edit etc.
- Rule 005: All acronyms, with the exception of those which form part of an identifier system business name,  MUST be upper case. For example 'NHS' or 'SDS'. Any acronyms used should be explained in the specification glossary.
- Rule 006: The order of the BusinessName segments when more than one is used SHOULD be logical and meaningful. For example 'ADW-Accept' should be used instead of 'Accept-ADW'
- Rule 007: The asset name MUST have a Version segment. The version number does not have leading or trailing zeros.

"
%}


**Examples**

- Profile names:
	- ITK-MessageHeader-2 **VALID**
	- CareConnect-ADW-Encounter-1 **VALID**
	- ITK-Related-Person-1 **INVALID** (Hyphen in resource name)
	- ITK-Read-Device-1 **INVALID** (CRUD function name)
	- ITK-device-1 **INVALID** (Incorrect capitalisation)
	- ADW-Discharge-Notice-Accept-Response-Message-Header-1 **INVALID** (Too many segments, and hyphen in resource name)

- Extension names:
	- Extension-CareConnect-GPC-EthnicCategory-1 **VALID**
	- Extension-ITK-MessageHandling-2 **VALID**
	- ITK-Participant-1 **INVALID** (No FHIRAssetName)

- OperationDefinition names:
	- GPConnect-RegisterPatient-Operation-1 **VALID**
	- eRS-Operation-1 **INVALID** (No OperationConstraint)

- Identifiers:
	- https://fhir.nhs.uk/Id/nhs-number **VALID**
	- https://fhir.nhs.uk/Id/localorganizationcode **INVALID** (No hyphens separating business names)

	

**Glossary**

***Business name:*** Business name is a string used to indicate the usage or purpose of the FHIR asset for a particular implementation or implementations.


[Pascal Case capitalization]: (https://msdn.microsoft.com/library/ms229043(v=vs.100).aspx)
[FHIR standard]: (http://hl7.org/fhir/)
[RFC2119]: (https://www.ietf.org/rfc/rfc2119.txt)
