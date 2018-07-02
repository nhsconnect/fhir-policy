---
title: Profiling
keywords: profiling
tags: [profiling]
sidebar: overview_sidebar
permalink: profiling.html
summary: Requirements for profiling FHIR resources
---

The FHIR standard provides a mechanism to specialise and extend FHIR resources through the creation of ["profiles"](https://www.hl7.org/fhir/profiling.html).

In England, we are developing profiles according to the below "levels":

- **Level 1**: These are the base FHIR resource profiles defined by HL7 international
- **Level 2**: These are referred to as 'Care Connect Profiles' and are England-wide profiles curated through the INTEROPen community, and published on the [HL7 UK FHIR reference server](https://fhir.hl7.org.uk)
- **Level 3**: These are implementation-specific profiles for a particular system or domain. For NHS Digital these are published on the [NHS Developer Network FHIR Reference Server](https://fhir.nhs.uk)

INTEROPen have defined further guidance on profiles in their [design decisions log](https://docs.google.com/spreadsheets/d/1PkdrXAML4z6attSrSnWF45ODFBZrjLA5PZw1R9q3Ttg/edit#gid=399932391).

NHS Digital has agreed to base any profiles on the Level 2 profiles where these exist (see requirement [FHIR-NAT-02](national-services.html)).

In addition, the following requirements have been agreed:

{% include requirement_box.html
	heading="FHIR-PROFILE-01: Profiles MUST NOT define alternate summary fields for resources"
	content="All FHIR resources (Level 1 profiles) have a numeber of fields defined as 'summary' fields, which appear in results when the client requested summary versions of the resource to be returned (for example in search results). These summary fields can only be defined in Level 1 profiles and cannot be changed in Level 2/3 profiles.

*Note: This is a rule established by HL7, but is not clear in the HL7 FHIR specification.*"
%}

