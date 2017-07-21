---
title: Conformance Requirements
keywords: conformance
tags: [conformance]
sidebar: overview_sidebar
permalink: conformance.html
summary: Requirements for FHIR endpoints to declare their capabilities
---

{% include requirement_box.html
	heading="FHIR-CONF-01: All FHIR ReST endpoints MUST publish their conformance"
	content="All servers offering a FHIR ReST API endpoint MUST publish a FHIR conformance / capability statement (in the form of a Conformance or CapabilityStatement resource) at the root URL of their endpoint.
<ul><li>For DSTU2 this is as per: <a href='http://hl7.org/fhir/DSTU2/conformance.html'>http://hl7.org/fhir/DSTU2/conformance.html</a></li>
<li>And for STU3 this is as per: <a href='https://www.hl7.org/fhir/capabilitystatement.html'>https://www.hl7.org/fhir/capabilitystatement.html</a></li>"
%}
