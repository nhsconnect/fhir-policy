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
	heading="FHIR-IDENT-01: Business IDs MUST only be used as the resource ID in ReST APIs when the system is the authoritative source of that entity"
	content="In some cases, where a system is acknowledged as the authoritative source of reference for a particular class of information, the need to do a lookup using a business ID to identify the logical ID of a resource may not be desirable. Equally, where the business ID is actually the primary key in a system for which the FHIR ReST API is simply a facade, generating another synthetic ID may not add any real value. In these cases, and ONLY in these cases, the business ID MAY be used as the logical ID for the resource exposed in a FHIR ReST API.
Currently, the only national resources this would apply to are:
<ul><li>Organisation (ODS Code)</li>
<li>Patient (NHS Number)</li>
<li>Prescription (Prescription ID)</li>
<li>Practitioner (SDS ID)</li></ul>
Clients must never assume a specific ID format when querying for resources."
%}
