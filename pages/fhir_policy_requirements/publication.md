---
title: Publication Requirements
keywords: publication
tags: [publication]
sidebar: overview_sidebar
permalink: publication.html
summary: Requirements for the publication of nationally defined FHIR API definitions
---

{% include requirement_box.html
	heading="FHIR-PUB-01: All FHIR resources and supporting assets held on Github"
	content="All FHIR resources relating to national systems and other nationally defined FHIR API profiles (including StructureDefinitions, ValueSets, OperationDefinitions, ImplementationGuides, etc.), as well as the source for API documentation (using Jekyll) MUST be published on a publicly available Github repository.
<p>Comments, feedback and suggestions from developers on FHIR resources (and associated documentation) SHOULD be managed through Github using the standard features for raising and tracking issues on the site.</p>"
%}

{% include requirement_box.html
	heading="FHIR-PUB-02: All FHIR resources published on a public FHIR reference server"
	content="All FHIR resources relating to national systems and other nationally defined FHIR API profiles (including StructureDefinitions, ValueSets, OperationDefinitions, ImplementationGuides, etc.) that are ready for external use (in either DRAFT or ACTIVE status) MUST also be made available the NHS Digital FHIR reference server [fhir.nhs.uk](https://fhir.nhs.uk). Test versions MAY also be published on the test FHIR server instance [fhir-test.nhs.uk](https://fhir-test.nhs.uk).
<p>Resources that are part of Care Connect (under the governance of INTEROPen) MUST also be published on a HL7 UK branded public FHIR server [fhir.hl7.org.uk](https://fhir.hl7.org.uk).</p>"
%}

{% include requirement_box.html
	heading="FHIR-PUB-03: All FHIR resource URIs must be resolvable URLs"
	content="All FHIR resources relating to national systems and other nationally defined FHIR API profiles (including StructureDefinitions, ValueSets, OperationDefinitions, ImplementationGuides, etc.) MUST have a URI that is a resolvable URL. Usually this will be the URL of the resource on the FHIR API reference server ([fhir.nhs.uk](https://fhir.nhs.uk) or [fhir.hl7.org.uk](https://fhir.hl7.org.uk))."
%}

{% include requirement_box.html
	heading="FHIR-PUB-04: FHIR API Maturity"
	content="When any FHIR API implementation guides are published (using Jekyll as per FHIR-PUB-01), they MUST have an associated maturity label. These labels will be taken from the GDS development process stages, and will be one of:

 - **Experimental**: Early development/POC version of an API for early sight during discovery
 - **Alpha**: Initial test APIs, likely to change substantially, or be discontinued as the project develops
 - **Beta**: APIs that are still under active development and subject to change, but that are likely to progress into a live API
 - **Release Candidate**: APIs that are largely complete, unlikely to change substantially, but still need further testing before becoming live
 - **Live**: Release live APIs
 - **Discontinued**: APIs which have been discontinued and should not be used for new development"
%}
