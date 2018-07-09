---
title: Publication Requirements
keywords: publication
tags: [publication]
sidebar: overview_sidebar
permalink: publication.html
summary: Requirements for the publication of nationally defined FHIR API definitions
---

FHIR API definitions will be developed and version controlled in public Git repositories, held on Github. This is used for the day-to-day development of new specifications and changes to existing specifications. This includes both formal FHIR profile resources, and also API implementation guide content assets. Those wishing to contribute towards the development of the API specifications themselves should do so through Github (by raising issues, pull requests, etc.)

{% include requirement_box.html
	identifier="FHIR-PUB-01"
	heading="FHIR-PUB-01: All FHIR resources and supporting assets held on Github"
	content="All FHIR resources relating to national systems and other nationally defined FHIR API profiles (including StructureDefinitions, ValueSets, OperationDefinitions, ImplementationGuides, etc.), as well as the source for API documentation (using Jekyll) MUST be held on a publicly available Github repository.
<p>Comments, feedback and suggestions from developers on FHIR resources (and associated documentation) SHOULD be managed through Github using the standard features for raising and tracking issues on the site.</p>"
%}

Once a specification is ready for wider review/use by implementors (even in early Experimental/Alpha status) it will be published onto the [NHS Developer network](https://developer.nhs.uk/apis) (and/or the HL7 UK / INTEROPen sites for CareConnect API assets). This will include the publication of FHIR profiles into the appropriate FHIR API reference server and publication of the API implementation guides. **Those wishing to implement APIs should refer to these published definitions rather than content held or published directly from Github.**

{% include requirement_box.html
	identifier="FHIR-PUB-02"
	heading="FHIR-PUB-02: All FHIR resources published on a public FHIR reference server"
	content="All FHIR resources relating to national systems and other nationally defined FHIR API profiles (including StructureDefinitions, ValueSets, OperationDefinitions, ImplementationGuides, etc.) that are ready for external use (in either DRAFT or ACTIVE status) MUST also be made available the NHS Digital FHIR reference server [fhir.nhs.uk](https://fhir.nhs.uk).

Resources that are part of Care Connect (under the governance of INTEROPen) MUST also be published on a HL7 UK branded public FHIR server [fhir.hl7.org.uk](https://fhir.hl7.org.uk)."
%}

{% include requirement_box.html
	identifier="FHIR-PUB-03"
	heading="FHIR-PUB-03: All FHIR resource URIs must be resolvable URLs"
	content="All FHIR resources relating to national systems and other nationally defined FHIR API profiles (including StructureDefinitions, ValueSets, OperationDefinitions, ImplementationGuides, etc.) MUST have a URI that is a resolvable URL. Usually this will be the URL of the resource on the FHIR API reference server ([fhir.nhs.uk](https://fhir.nhs.uk) or [fhir.hl7.org.uk](https://fhir.hl7.org.uk))."
%}

{% include requirement_box.html
	identifier="FHIR-PUB-04"
	heading="FHIR-PUB-04: FHIR API Maturity"
	content="When any FHIR API implementation guides are published (using Jekyll as per FHIR-PUB-01), they MUST have an associated maturity label. These labels are based on the GDS development process stages, and will be one of:

 - **Experimental**: Early development/proof of concept version of an API for early sight during discovery.
 - **Alpha**: Initial test APIs, likely to change substantially.
	- Typical Usage: Engagement with others interested in being involved with early development work and influencing the direction taken.
 - **Beta**: APIs that are still under active development and subject to change
	- Typical Usage: Engagement with 'first of type' or early adopters by the creation of first of type or pilot systems for testing, proof of concept etc. This development can assist in progression to a release candidate for a wider rollout.
 - **Release Candidate**: APIs that are largely complete, unlikely to change substantially, but still need further testing by a wider group of implementers before becoming live.
	- Typical Usage: After having been previously implemented by 'first of type' or pilot sites and now to be rolled out to a wider group of implementers.
 - **Live**: Release live APIs
 - **Discontinued**: APIs which have been discontinued and should not be used for new development"
%}

