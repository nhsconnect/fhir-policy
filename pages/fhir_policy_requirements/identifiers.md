---
title: Identifiers
keywords: identifiers
tags: [identifiers]
sidebar: overview_sidebar
permalink: identifiers.html
summary: Requirements for identifiers in FHIR resources
---

In the FHIR standard, every resource has a unique identifier for that resource instance. According to the FHIR specification: “Each resource has an "id" element which contains the logical identity of the resource assigned by the server responsible for storing it.”. This identifier will differ if the resource is moved or persisted on another server (it is analogous to the primary key in a database). Typically, a resource will also have one or more “business” identifiers. These have a business meaning outside the FHIR server (e.g. an NHS number or Organisation Identifier), and can be used in resources held on multiple servers (each instance of which would have different logical IDs to identify them). See: [https://www.hl7.org/fhir/resource.html](https://www.hl7.org/fhir/resource.html)

{% include requirement_box.html
	identifier="FHIR-IDENT-01"
	heading="FHIR-IDENT-01: Business IDs MUST only be used as the resource ID in ReST APIs when the system is the authoritative source of that entity"
	content="In some cases, where a system is acknowledged as the authoritative source of reference for a particular class of information, the need to do a lookup using a business ID to identify the logical ID of a resource may not be desirable. Equally, where the business ID is actually the primary key in a system for which the FHIR ReST API is simply a facade, generating another synthetic ID may not add any real value. In these cases, and ONLY in these cases, the business ID MAY be used as the logical ID for the resource exposed in a FHIR ReST API.
Currently, the only national resources this would apply to are:

- Organisation (ODS Code)
- Patient (NHS Number)
- Prescription (Prescription ID)
- Practitioner (SDS ID)
- National eReferral request (UBRN)

Clients must never assume a specific ID format when querying for resources."
%}

Where resources include references to other resources, there is also a need to consider how these references would be represented to ensure clients are able to follow them and find referenced resources. The preferred approach to this differs depending on the FHIR Paradigm used:

{% include requirement_box.html
	identifier="FHIR-IDENT-02"
	heading="FHIR-IDENT-02: FHIR Documents: Documents SHOULD contain referenced resources"
	content="When using the FHIR Document Paradigm, wherever possible referenced resources should always be contained in the composition so that recipients have all the information needed to interpret and act on the content of the document. This also means that the recipient is confident that all included resources are the versions that were the latest at the time the document was created. Within a document, resources can reference each other, these references are meaningless outside the document however. Note: References between resources within a document can include circular references – this should be taken into account when parsing."
%}

{% include requirement_box.html
	identifier="FHIR-IDENT-03"
	heading="FHIR-IDENT-03: FHIR Messaging: References in messaging SHOULD be logical references"
	content="When using the FHIR Messaging Paradigm, it is likely messages will include references to external resources. These references SHOULD use an identifier from a known NamingSystem. This is known as a [logical reference](https://www.hl7.org/fhir/references.html#logical) in the FHIR standard. The NamingSystem URI SHOULD be searchable on a FHIR Reference server to return the NamingSystem resource that describes the identifiers used (for example: [https://fhir.nhs.uk/NamingSystem](https://fhir.nhs.uk/NamingSystem)).
"
%}

An example of a logical reference would be the below (for an ODS code):
```json
"identifier": {
  "system": "http://fhir.nhs.uk/Id/ods-organistion-code",
  "value": "T1430"
  "display": "Health and Social Care Information Centre"
}
```

{% include requirement_box.html
	identifier="FHIR-IDENT-04"
	heading="FHIR-IDENT-04: FHIR ReST: References between ReST resources SHOULD be literal references but MAY be logical references"
	content="When using the FHIR ReST Paradigm, resources will SHOULD reference other resources via URL (i.e. a [literal reference](https://www.hl7.org/fhir/references.html#literal) in the FHIR standard). The resource owner should (where possible) only reference other resources that they can be relatively confident consumers of their API will be able to resolve and retrieve. For referencing other things outside this, a logical reference SHOULD be used.

Note: URL references to other resources will (by default) return the latest version of the referenced resource. If this isn't desirable, the resource owner may either contain the resource or use a versioned URL as a literal reference.
"
%}

An example of a literal reference would be the below (also for an ODS code):
```json
"onBehalfOfReference": {
  "reference": "https://directory.spineservices.nhs.uk/STU3/Organization/T1430",
  "display": "Health and Social Care Information Centre"
}
```
