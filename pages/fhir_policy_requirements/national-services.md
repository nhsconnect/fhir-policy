---
title: National Services
keywords: national services
tags: [national services]
sidebar: overview_sidebar
permalink: national-services.html
summary: Requirements for FHIR in national services delivered by NHS Digital
---

In addition to the general requirements for the use of FHIR nationally, there are also some specific requirements for the national services delivered by NHS Digital that use FHIR APIs.

{% include requirement_box.html
	identifier="FHIR-NAT-01"
	heading="FHIR-NAT-01: National FHIR resources MUST use consistent URLs"
	content="In order to support the move to FHIR across a range of national services, there is a need to define a URL scheme which will allow entities such as Patients and Organisations to be referenced reliably even when the relevant national FHIR services have not yet been implemented. These URLs should also support a future move to Internet-facing services, and as such it should be possible to resolve them over both the Internet and N3/HSCN as applicable.

The below URLs SHOULD be used for national services where possible:

- https://demographics.spineservices.nhs.uk  (Spine Demographics: PDS, V&M)
- https://clinicals.spineservices.nhs.uk (Spine Clinicals: SCR, FGM, CPIS, etc.)
- https://prescriptions.spineservices.nhs.uk (EPS)
- https://directory.spineservices.nhs.uk (ODS – and possibly other directory data in future)

**IMPORTANT NOTE**: This requirement is to promote alignment across NHS Digital, but until individual services are developed there is still a risk that these URLs may change.

Spine DevOps should be informed of any subdomains being added under spineservices.nhs.uk via Service Request in the NHS Digital Cherwell system. The subdomain creation task will then be passed onto the DNS team by Spine DevOps."
%}

A 'Care Connect' Profile is a FHIR profile that is owned and governed by INTEROPen and hosted by [HL7 UK](https://fhir.hl7.org.uk/).

{% include requirement_box.html
	identifier="FHIR-NAT-02"
	heading="FHIR-NAT-02: NHS Digital MUST adopt Care Connect profiles where possible"
	content="NHS Digital will use the Care Connect Profiles as their base FHIR Profiles and derive NHS Digital Profiles from the Care Connect Profiles wherever possible.

Because Care Connect profiles contain a large number of optional fields, in some cases an NHS Digital profile that extends a Care Connect profile may choose to remove an optional field (i.e. make it's cardinality 0..0). The general principle that will be applied to decide if this is appropriate is:

- If you know you'll never need it, profile it out
- If you know you might need it, leave it in
- If you aren't sure - assess whether there is a possibility that it could become useful in future - if there's no reason you can come up with, you can profile it out, otherwise leave it in.
"
%}
