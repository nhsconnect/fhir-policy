---
title: Versioning Requirements
keywords: versioning
tags: [versioning]
sidebar: overview_sidebar
permalink: versioning.html
summary: Requirements for versioning of FHIR resources and endpoints
---

{% include requirement_box.html
	heading="FHIR-VER-01: Versioning of Profiles and Resources"
	content="Nationally defined FHIR profiles will be versioned during development using Git, and this will follow the standard GitFlow model.
The versioning for published artefacts will broadly follow “semantic versioning” standards: http://semver.org/ 
The major and minor versions will be visible, and the patch version MAY also be exposed.
Version numbers held in profiles and resource instanced MUST therefore be in one of the following forms:
<br/>MAJOR – e.g. 1
<br/>MAJOR.MINOR – e.g. 1.0
<br/>MAJOR.MINOR.PATCH – e.g. 1.0.2"
%}

Definitions:

- Minor Change
   - A minor change is defined as a backwards-compatible change which is not expected to break existing implementations. Examples include:
      - Addition of new optional fields in a profile
      - Addition of new operations whose name does not clash with existing operations
- Major Change
   - This is a breaking change, and as such, implementers will need to understand the changes that have been made in the new version, and make changes to their implementations if required.
- Resources
   - The versioning requirements relate to all resources served up from FHIR compliant endpoints. This include FHIR “profile” resources published nationally – including StructureDefinitions, ValueSets, OperationDefinitions, ImplementationGuides, Conformance Statements, etc.

{% include requirement_box.html
	heading="FHIR-VER-02: HL7 FHIR version in FHIR Endpoint URL"
	content="Nationally delivered FHIR endpoints (i.e. servers that implement FHIR standards to serve FHIR resources or respond to calls to FHIR operations), including FHIR messaging endoints, MUST differentiate the HL7 FHIR version (e.g. DSTU2, STU3, etc) in the FHIR base URL.
<p>This MUST follow the format: <b>https://[baseurl]/[fhir-version]</b></p>
<p>Where <b>[fhir-version]</b> is the uppercase alphanumeric major version name of the FHIR version in use (e.g. DSTU2 or STU3) – see <a href='http://hl7.org/fhir/directory.html'>this page</a> for published versions.
Where the <b>[fhir-version]</b> is missing, clients MUST assume the version is DSTU2.</p>
<p>NOTES:
<ul><li>This also applies to the public FHIR API reference servers, which will publish profiles on URLs which follow this convention.</li>
<li>The baseurl part may be just an FQDN, but may also have other path elements if required to uniquely identify the endpoints (e.g. where a system services requests relating to multiple organisations, an organisation code may form part of the baseurl).</li></ul>
</p>"
%}

{% include requirement_box.html
	heading="FHIR-VER-03: Versioning of FHIR endpoint implementations"
	content="In addition to the HL7 FHIR version used, and the versioning of nationally published profiles, systems implementing those profiles in actual system endpoints will also want to be able to version those endpoints as they release new functionality or make changes to the resources they support in their endpoint.
This endpoint version will also be conveyed in the URL, and MUST follow the FHIR version in the URL path. The format of the version identifier will be defined by the implementer and could be in any URL-valid format. The combined structure of the URL will therefore be:
<p><b>https://[baseurl]/[fhir-version]/[endpoint-version]</b></p>
<p>NOTE: Some FHIR endpoint implementations may choose to be 'versionless' – i.e. they will always maintain full backwards compatibility between releases. In these cases the endpoint version can be omitted. An example of this is the FHIR API Reference Servers used to publish national profiles. These reference servers require stable and reliable URLs for profiles, so will not include an endpoint version in the URL.</p>"
%}

{% include requirement_box.html
	heading="FHIR-VER-04: Major Profile Version in Resource ID"
	content="Nationally defined FHIR profile resources MUST include the major version number in the logical resource ID.
This is declared within the resource in the URL field, so version 1.X.X of a StructureDefinition for Patient would contain a URL like this:
<p><b>&lt;url value='https://[baseurl]/[fhir-version]/StructureDefinition/mypatient-1'/&gt;</b></p>
<p>The logical ID for this resource is therefore mypatient-1, with the 1 denoting that the major version is 1.</p>
<p>NOTES:</p>
<ul>
<li>When this profile is retrieved from the URL above, the latest minor/patch version within the 1.X.X range will be returned (as per the FHIR standard).</li>
<li>The filename for this resource in source control MAY also reflect this, and include the major version in the filename (for example, the above resource could be called MyPatient-1.xml)</li>
</ul>
<p>As an example, a valid URL following the above policies could be:</p>
<p><b>https://fhir.nhs.uk/STU3/StructureDefinition/mypatient-1</b></p>"
%}

{% include requirement_box.html
	heading="FHIR-VER-05: Minor and Patch Profile Version will use FHIR versioning"
	content="In order to publish and ensure minor and patch versions are also available, the standard FHIR versioning mechanism MUST be used within the FHIR API Reference Servers (used to publish profiles nationally). This will be linked with the version element within the resource.
<p>The version element within the resource will contain the full semantic version of the resource, and will look like this:</p>
<p><b>&lt;version value='1.1.3'/&gt;</b></p>
<p>This will be linked with the versioning mechanism for resourced defined in the FHIR specification for FHIR ReST endpoint, which will allow the FHIR HISTORY and VREAD operations to be used to retrieve specific versions of profiles.</p>
<p>The FHIR VREAD operation MUST be supported for nationally published FHIR profiles, to allow a specific version of a profile to be retrieved – for example, to retrieve version 1.1.3 of the mypatient-1 resource you would use a call to: <b>https://[baseurl]/[fhir-version]/StructureDefinition/mypatient-1/_history/1.1.3</b></p>
<p>NOTE:</p>
<ul><li>This versioned URL MAY also be used in individual resource instances created by implementing systems to declare their conformance to a specific MAJOR.MINOR.PATCH version, by including the versioned URL in the profile element at the top of their resource instance.</li>
<li>Alternatively, the basic un-versioned URL can be used to declare conformance with the latest MAJOR.*.* version of the profile.</li></ul>"
%}
