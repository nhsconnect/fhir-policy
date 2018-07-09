---
title: FHIR Policy Release Notes
keywords: FHIR Policy Overview, Release Notes
tags: [release]
sidebar: overview_sidebar
permalink: overview_release_notes.html
summary: "Release notes outlining changes to the FHIR Policy."
---

Note - versions of this policy follow [semantic versioning](http://semver.org/) - minor and patch versions should be considered as non-breaking.

The latest unstable in-progress version of this specification can be found on [github pages](https://nhsconnect.github.io/fhir-policy/).

Those wanting to contribute to the development of the specification can raise issues and pull requests via the [git repository](https://github.com/nhsconnect/fhir-policy).

#### 1.4.0-beta (2nd July 2018)

- Added profiles page clarifying "levels" and specifying the requirement around the use of summary fields in profiles
- Added ability to hyperlink to individual requirements on pages

#### 1.3.1-alpha (28th March 2018)

- Added comment to FHIR-NAT-01 clarifying that new Spine subdomains must be approved by the Spine DevOps team

#### 1.3.0-alpha (22nd March 2018)

- Updated naming policy statements to clarify that they cover the name, ID and filename for national profiles
- Updated naming policy for OperationDefinitions (FHIR-NAME-05) to reflect the operation action in the name
- Added some clariying paragraphs on the publication page to clarify the roles of Github and the NHD Developer network
- Added requirement FHIR-SERIAL-03 to clarify that custom XML namespaces outside those defined in the FHIR spec must not be used
- Added UBRN in the list of examples of allowable national business identifiers also used as logical identifiers in requirement FHIR-IDENT-01
- Added FHIR-CONF-02 to require CapabilityStatements for national services to conform to a national profile, with supporting guidance

#### 1.2.0-alpha (7th December 2017)

- Altered wording on FHIR-PUB-04 to further clarify the meaning of the maturity labels
- Added requirement FHIR-VER-06 for major versioning in profiles when moving to a new FHIR version
- Added requirement FHIR-NAT-01 to confirm URLs for national FHIR services
- Added requirement FHIR-NAT-02 to state that NHS Digital will use Care Connect profiles where possible, and clarify the principles for removing optional fields
- Added requirements FHIR-NAME-01 to FHIR-NAME-05 for naming conventions

#### 1.1.0-alpha (9th November 2017)

- Added requirement: FHIR-PUB-04 FHIR API Maturity
- Added requirements: FHIR-OPER-01 and FHIR-OPER-02 covering the use of custom operations in ReST endpoints
- Added this release notes page

#### 1.0.0-alpha (21st July 2017)

- First Alpha release of FHIR Policy

