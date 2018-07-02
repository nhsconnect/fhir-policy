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
	identifier="FHIR-SERIAL-01"
	heading="FHIR-SERIAL-01: FHIR ReST APIs MUST support JSON serialisation"
	content="All FHIR ReST endpoints MUST support JSON formatted requests/responses.
FHIR ReST endpoints SHOULD also support XML formatted requests/responses.
The serialisation mime-types supported MUST be declared in the Conformance/CapabilityStatement resource for the endpoint, and the server MUST use the usual FHIR mechanisms to allow clients to request a specific Content Type as per the FHIR spec (servers may choose to reject the use of XML if it is not supported)."
%}

{% include requirement_box.html
	identifier="FHIR-SERIAL-02"
	heading="FHIR-SERIAL-02: FHIR Messaging Interfaces MUST support XML serialisation"
	content="All FHIR messaging endpoints MUST support XML formatted requests/responses.
FHIR messaging endpoints SHOULD also support JSON formatted requests/responses.
The serialisation mime-types supported MUST be declared in the Conformance/CapabilityStatement resource for the messaging endpoint."
%}

{% include requirement_box.html
	identifier="FHIR-SERIAL-03"
	heading="FHIR-SERIAL-03: Namespaces outside those defined in the FHIR specification MUST NOT be used"
	content="The FHIR standard [specifies a specific namespace](http://hl7.org/implement/standards/fhir/xml.html) for FHIR XML elements, with a second namespace for XHTML content in narrative sections. Those specifying FHIR APIs MUST not use other namespaces in their APIs"
%}

