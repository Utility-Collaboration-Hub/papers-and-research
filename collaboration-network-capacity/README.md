# Proposed data standards for infrastructure forward plans and network capacity reporting: extending the MUDDI model

> A discussion paper proposing a "Coordination and Capacity" use case as a specialisation of the OGC MUDDI model, with reference logical data models to support the coordination of infrastructure works and the reporting of network capacity.

**Prepared by:** Dr Neil Brammall, Chris Carlon

**Contact:** [utilitycollaboration@utilityinformationservices.com](mailto:utilitycollaboration@utilityinformationservices.com)

**Version:** Published 1.0 — 26/07/2026

---

## Executive Summary

MUDDI – the Open Geospatial Consortium (OGC) Model for Underground Data Definition and Integration – defines a core and an extended Conceptual Model of feature classes that allows the integration of datasets from different types of information about the underground space, using different information models.

There are a number of established and emerging implementations of MUDDI in different countries and addressing different use cases.

It is proposed that a "Coordination and Capacity" use case for maintaining and extending utility networks would be a productive specialisation of the MUDDI model. This proposal is based on extensive evidence that the coordination of works is a priority area across different geographies, and that the knowledge and re-use of existing infrastructure capacity for the installation of new assets is an important driver of coordination, collaboration and operational efficiency.

Governments and regulators around the world see the benefits of works coordination in terms of cost-effectiveness and minimisation of disruption to citizens, and devote time and effort to defining incentives and regulations to encourage collaborative behaviour. There is also clear evidence that the knowledge of existing network capacity is a key contributor to coordination in supporting reuse of existing infrastructure. In addition, understanding existing and future network capacity is a key enabler for other infrastructure development.

While defining standards to consistently describe the information requirements for this area does not on its own unlock barriers to coordination and collaboration, such standards are critical when considering the need for consistent data exchange in different geographies and regulatory regimes, across sectors and between multiple organisations with different roles and priorities across different projects, and may contribute to an ecosystem of tools and processes that support the necessary data sharing and transparency that are enablers to effective coordination. Data standardisation will not solve this problem on its own, but the problem will not be solved comprehensively and at scale without data standards.

A particular approach to this work is proposed. There is a significant gap between the definition of a Conceptual data model and the development of an implementation that conforms to that model. With little or no direction as to how a specific implementation may be developed, there may be little in common and weak interoperability between different independent implementations, even for a similar use case.

As a general approach to extending the MUDDI model or defining additional use cases, it is recommended that reference Logical Models should be developed and published to help fill this gap between concept and implementation and provide guidance and consistency for other implementers of the MUDDI model. The use cases outlined in this proposal provide a set for which Logical Models can be defined, and these may provide an exemplar and test case for this approach which may then be adopted for future developments.

Finally, there are likely to be particular sensitivities and security considerations around the representation of data supporting coordination and reuse of existing capacity. The availability of such information, and the appropriate level of detail, will likely be driven by the identity and role of the requestor, and the purpose for which they are requesting the data. Implementation of Coordination and Capacity use cases will therefore provide an opportunity to explore the representation of suitable attribution to support granular purpose-driven access control, and entities that allow the proper representation of the criteria to be used in granting or denying access, or modifying the response in terms of data scope and level of detail.

## Recommendations

The following recommendations are made:

- To seek feedback on this paper and form a community of interest.
- To define in greater detail the use cases outlined in this paper.
- To design logical data models that serve the specified use cases.
- To include consideration of attribution relating to data sensitivity and security such that the data can form the basis for the implementation of granular access controls, based on user identity and context (including use case/purpose).
- To validate and test the logical models using representative data and expert review.
- To publish a test and validation report describing the use cases, logical data models and the results of the testing.
- Depending on the outputs of the validate and test phase, publish reference logical data models conforming to the MUDDI Conceptual Model, ideally via the MUDDI Standards Working Group.
- Develop recommendations for the applicability of this approach for future extensions and use cases for MUDDI for consideration by the MUDDI Standards Working Group.

---

*For the full paper*, see [here](https://github.com/Utility-Collaboration-Hub/papers-and-research/blob/b85ed3aeae089bde0688cd418942e80beb60539f/collaboration-network-capacity/Utility%20and%20Infrastructure%20Coordination%20and%20Capacity%20-%20Data%20Standardisation%20-%20Publish.pdf).
