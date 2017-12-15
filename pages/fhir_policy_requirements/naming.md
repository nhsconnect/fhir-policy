---
title: Naming
keywords: naming
tags: [naming]
sidebar: overview_sidebar
permalink: naming.html
summary: Naming conventions for nationally defined FHIR profiles
---

In order to promote consistency and make it easier for implementers to locate suitable profiles for their projects, a naming strategy will be adopted for nationally defined FHIR profiles.

{% include requirement_box.html
	heading="FHIR-NAME-01: FHIR Profile names MUST follow an agreed format"
	content="The name of the profile refers to name.value element in the profile structured definition and the profile structured definition filename. The name of the profiles consists of a number of name segments, and shall be in the form:

**[Base]-[BusinessName1]-[BusinessName2]-[FHIRResourceName]-[Version]**

The segments are defined to as follows:

- **Base**: The base type if one is used. Optional but mandatory for CareConnect derived profiles.
- **BusinessName1**: The first business name of the profile. The resource name MUST have at least one BusinessName segment if BaseType is not populated. For example 'ADW', 'SPINE' etc. Where a resource may be used across several domains business names should reflect that.
- **BusinessName2**: The second business name of the profile. The resource name MAY have a second BusinessName segment. Where there is a second business name each BusinessName MUST be separated by a hyphen (-) character. For example 'ADW-Response'.
- **FHIRResourceName**: The name of the base FHIR resource. Mandatory
- **Version**: This is the major version number of the profile. Mandatory

For example: CareConnect-ADW-Encounter-1"
%}

{% include requirement_box.html
	heading="FHIR-NAME-02: FHIR ValueSet names MUST follow an agreed format"
	content="This section details a set of rules that MUST be followed when creating NHS Digital FHIR value sets. The name of the value set consists of a number of name segments and shall be in the form:

**[Base]-[BusinessName1]-[BusinessName2]-[FHIRResourceName]-[Version]**

The segments are defined to as follows:

- **Base**: The base ValueSet if one is used. Optional but mandatory for CareConnect derived ValueSets
- **BusinessName1**: The first business name of the ValueSet. The resource name MUST have at least one BusinessName segment if BaseType is not populated. For example 'ADW', 'SPINE' etc. Where a resource may be used across several domains business names should reflect that.
- **BusinessName2**: The second business name of the ValueSet. The resource name MAY have a second BusinessName segment. Where there is a second business name each BusinessName MUST be separated by a hyphen (-) character. For example 'ADW-EncounterType'.
- **Version**: This is the major version number of the ValueSet. Mandatory

For example: CareConnect-ReligiousAffiliation-1
"
%}

{% include requirement_box.html
	heading="FHIR-NAME-03: FHIR Extension names MUST follow an agreed format"
	content="This section details a set of rules that MUST be followed when creating NHS Digital FHIR Extensions. The name of the extension consists of a number of name segments and shall be in the form:

**Extension-[Base]-[BusinessName1]-[BusinessName2]-[Version]**

The segments are defined to as follows:

- **Base**: The base extension if one is used. Optional but mandatory for CareConnect derived extensions.
- **BusinessName1**: The first business name of the extension. The resource name MUST have at least one BusinessName segment if BaseType is not populated. For example 'ADW', 'SPINE' etc. Where a resource may be used across several domains business names should reflect that.
- **BusinessName2**: The second business name of the extension. The resource name MAY have a second BusinessName segment. Where there is a second business name each BusinessName MUST be separated by a hyphen (-) character. For example 'ADW-EncounterType'.
- **Version**: This is the major version number of the extension. Mandatory

For example: Extension-CareConnect-ConditionEpisode-1
"
%}

{% include requirement_box.html
	heading="FHIR-NAME-04: FHIR OperationDefinition names MUST follow an agreed format"
	content="OperationDefinitions should be named using the following segment name format:

**[Base]-[BusinessName]-[OperationConstraint]-[OperationDefinitionKind]-[Version]**

The segments are defined to as follows:

- **Base**: The base operation definition if one is used. Optional but mandatory for CareConnect derived operation definitions.
- **BusinessName**: A business name for the operation definition. Optional.
- **OperationConstraint**: The operation constraint. Mandatory. An example of an OperationConstraint is 'CareRecord'.
- **OperationDefinitionKind**: Choice of 'Operation' or 'Query' fixed character strings. Mandatory.
- **Version**: This is the major version number of the operation definition. Mandatory"
%}



{% include requirement_box.html
	heading="FHIR-NAME-05: General naming conventions MUST also be followed"
	content="The following additional rules MUST also be adhered to for naming profile resources (StructureDefinitions, ValueSets, etc):

- Rule 001: NHS Digital FHIR name segments MUST be human understandable. This means that the name must give a clear indication of the purpose or usage of the resource.
- Rule 002: NHS Digital FHIR resource names MUST follow the Pascal Case capitalization convention and MUST be alphanumeric format only. In the Pascal Case capitalization convention, the first letter in each segment name and of each subsequent compound word must be capitalized. For example BackColor. See [here](https://msdn.microsoft.com/library/ms229043(v=vs.100).aspx) and [here](https://en.wikipedia.org/wiki/CamelCase)
- Rule 003: To improve the readability of long NHS Digital FHIR resource names, each string segment used to build an NHS Digital FHIR resource name, MUST be separated using the hyphen (-) character. For example :- BaseType-BusinessName1-BusinessName2-FHIRResourceName-VersionOfProfile OR BaseType-BusinessName1-FHIRResourceName-VersionOfProfile
- Rule 004: CRUD function names MUST NOT be used in NHS Digital FHIR resource names. These are Create, Read, Update and Delete. Other variations should be avoided for example Retrieve, Modify, Edit etc.
- Rule 005: All acronyms MUST be upper case. For example 'NHS' or 'SDS'. Any acronyms used should be explained in the specification glossary.
- Rule 006: The order of the BusinessName segments when more than one is used SHOULD be logical and meaningful. For example 'ADW-Response' should be used instead of 'Response-ADW'
- Rule 007: The resource name MUST have a Version segment. The version number does not have leading or trailing zeros.
- Rule 008: The resource name MUST conform to the following regex ((?:[A-Z0-9][a-zA-Z0-9]\*-)?)((?:[A-Z0-9][a-zA-Z0-9]\*-)?)((?:[A-Z0-9][a-zA-Z0-9]\*-)?)([1-9]\*) Note: conformance to this regex does not guarantee a valid resource name. 
"
%}


Examples:

- Structure Definitions:
	- ITK3-DocumentReference-1 **VALID**
	- CareConnect-ADW-Encounter-1 **VALID**
	- ITK3-Related-Person-1 **INVALID** (Hyphen in resource name)
	- ITK3-Read-Device-1 **INVALID** (CRUD function name)
	- ITK3-device-1 **INVALID** (Incorrect capitalisation)
	- ADW-Discharge-Notice-Accept-Response-Message-Header-1 **INVALID** (Too many segments, and hyphen in resource name) 

