---
title: Serialisation
keywords: serialisation
tags: [serialisation]
sidebar: overview_sidebar
permalink: serialisation.html
summary: Requirements for FHIR content types
---

The FHIR standard allows a number of serialisations of resources to be used. Ideally, servers will support the two main serialisations – XML and JSON, however there may be cases where this is difficult to achieve.

{% include requirement_box.html
	heading="FHIR-SERIAL-01: FHIR ReST APIs MUST support JSON serialisation"
	content="All FHIR ReST endpoints MUST support JSON formatted requests/responses.
FHIR ReST endpoints SHOULD also support XML formatted requests/responses.
The serialisation mime-types supported MUST be declared in the Conformance/CapabilityStatement resource for the endpoint, and the server MUST use the usual FHIR mechanisms to allow clients to request a specific Content Type as per the FHIR spec (servers may choose to reject the use of XML if it is not supported)."
%}

{% include requirement_box.html
	heading="FHIR-SERIAL-02: FHIR Messaging Interfaces MUST support XML serialisation"
	content="All FHIR messaging endpoints MUST support XML formatted requests/responses.
FHIR messaging endpoints SHOULD also support JSON formatted requests/responses.
The serialisation mime-types supported MUST be declared in the Conformance/CapabilityStatement resource for the messaging endpoint."
%}

