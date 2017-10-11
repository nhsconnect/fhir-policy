---
title: FHIR Operations
keywords: operations
tags: [operations]
sidebar: overview_sidebar
permalink: operations.html
summary: Requirements for the use of custom operations in FHIR
---

When deploying a FHIR ReST endpoint, the FHIR standard defines the standard operations that can be carried out on individual resources (read, vread, search, etc), resource types, or globally on a server. In addition, FHIR provides a mechanism to define custom operations.

Custom operations are typically used when unusual or bespoke behaviours are required, and can sometimes be used when multiple resources need to be updated together as part of a wider workflow. These can be considered a form of "remote procedure call", and if custom operations are used, the implementor must clearly define what the operation does and how it should be used (using an OperationDefinition resource).

{% include requirement_box.html
	heading="FHIR-OPER-01: Where a request maps to a standard FHIR operation, the standard operation SHOULD be used"
	content="Where a server wants to allow resources to be accessed or updated in a way that aligns with the standard operations defined in the FHIR standard (e.g. querying for appointment slots, retrieving medications and including the associated patient resources, etc.) then using the standard FHIR ReST operations makes implementation simpler for clients using standard FHIR libraries and tools, so should be used."
%}

{% include requirement_box.html
	heading="FHIR-OPER-02: Where a request requires multiple resources to be changed under the control of the client, then an operation (or transaction) constructed by the client MAY be used"
	content="In these cases, the server doesn't and shouldn't need to understand the business logic being implemented by the client, for example:

Client: I want to book an appointment, and a blood test for the same morning. I also want to reserve a parking space for that whole day.

If any of these three fail, then book nothing.

Server: Okay, I don't what business rules link these three, but I'll carry out your transaction as requested."
%}

{% include requirement_box.html
	heading="FHIR-OPER-03: Where a request relates to one resource under the control of the client, but which could impact other resources under the control of the server, then standard FHIR ReST operarions SHOULD be used."
	content="In these cases, the server has its own business logic rules to implement, can manage it's own transactional integrity, and the client can't know or influence what these might be, for example:

Client: I want to book the 09:35 appointment please.

Server: Okay, that's booked, which means that slot is full so I will also update the status of the associated slot. It was the last available slot, so it also means I need to roster more staff for that day and then create another schedule with more slots."
%}

