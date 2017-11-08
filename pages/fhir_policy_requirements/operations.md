---
title: FHIR Operations
keywords: operations
tags: [operations]
sidebar: overview_sidebar
permalink: operations.html
summary: Requirements for the use of custom operations in FHIR ReST endpoints
---

When deploying a FHIR ReST endpoint, the FHIR standard defines the standard ReSTful operations that can be carried out on individual resources (read, vread, search, etc), resource types, or globally on a server.

The target architectural model for a FHIR endpoint is ReST as described [here](https://www.hl7.org/fhir/http.html). Therefore, designers of FHIR APIs should seek to align with this model, and make use of RESTful CRUD operations.

{% include requirement_box.html
	heading="FHIR-OPER-01: Where a request maps to a standard FHIR operation, the standard operation SHOULD be used"
	content="Use of standard FHIR ReST operations makes implementation simpler for clients using standard FHIR libraries and tools, so should be used where possible.

This is appropriate where a server wants to allow resources to be accessed or updated in a way that aligns with the standard operations defined in the FHIR standard. Examples of use-cases where standard ReST operations may be appropriate:

- Querying for appointment slots.
- Booking an appointment, and updating the associated slot to make it unavailable for others to book.
- Retrieving medications and including the associated patient resources."
%}

In addition, FHIR provides a mechanism to define custom operations as described [here](https://www.hl7.org/fhir/operations.html). FHIR custom operations follow an RPC architectural model. Ideally APIs should seek to avoid a mixture of architectural styles however it is recognised that deviations from the RESTful model are applicable in certain circumstances.

{% include requirement_box.html
	heading="FHIR-OPER-02: More complex and behaviours involving updates to multiple resources or complex querying or composition of resources MAY use an RPC-style FHIR Operation"
	content="Examples of cases where a custom operation may be appropriate:

 - Where the server needs to play an active role in formulating the content of the response, not merely return existing information.
 - Where the intended purpose is to cause side effects such as the modification of existing resources, or creation of new resources.
 - Where a request requires multiple resources to be changed under the control of the client as part of a single atomic transaction.
 - When unusual or bespoke behaviours are required which can't easily be achieved using ReSTful operations.
 - Where there is a requirement to bring back multiple resource types where each resource type had its own specific selection criteria, perhaps also with each of the resources also bringing back associated linked resources."
%}

