# Proposed data standards for infrastructure forward plans and network capacity reporting: extending the MUDDI model

**Prepared by:**
Dr Neil Brammall
Chris Carlon
E-mail: [utilitycollaboration@utilityinformationservices.com](mailto:utilitycollaboration@utilityinformationservices.com)

26/07/2026

*Utility Information Services — Published 1.0*

---

## Report Issue / Amendment Record

**Report Title:** Proposed data standards for infrastructure forward plans and network capacity reporting: extending the MUDDI model

### Amendment Details

| Issue | Description of Amendment | Originator / Author |
|-------|--------------------------|---------------------|
| Published 1.0 | First published version | Neil Brammall, Chris Carlon |

---

## Acknowledgements

The authors would like to thank the following individuals for their review of, and valuable contributions to, this paper:

| Name | Organisation | Country/Region |
|------|--------------|----------------|
| Mujahed Abdullah Alabdan | Riyadh Infrastructure Projects Center | Riyadh, Saudi Arabia |
| Abdullah Ali Alasmari | Riyadh Infrastructure Projects Center | Riyadh, Saudi Arabia |
| Abdullah Nasser Almashari | Riyadh Infrastructure Projects Center | Riyadh, Saudi Arabia |
| Raghad Bandar Alfadhliah | Riyadh Infrastructure Projects Center | Riyadh, Saudi Arabia |
| Paul Churcher | Department of National Defence | Ottawa, Canada |
| Kevin Ferguson | Durham County Council | Durham, England |
| Holger Kessler | AtkinsRéalis | UK |
| Alan Leidner | GISMO | New York City, USA |
| Carsten Roensdorf | Ordnance Survey | Great Britain |

---

## Contents

1. [Executive Summary](#1-executive-summary)
2. [Introduction](#2-introduction)
   - 2.1 [Purpose](#21-purpose)
   - 2.2 [Why coordination and capacity?](#22-why-coordination-and-capacity)
     - 2.2.1 [What do we mean by capacity?](#221-what-do-we-mean-by-capacity)
3. [The problem: a UK perspective](#3-the-problem-a-uk-perspective)
4. [Evidence for action](#4-evidence-for-action)
5. [Use cases](#5-use-cases)
   - 5.1 [Coordination use cases](#51-coordination-use-cases)
   - 5.2 [Capacity use cases](#52-capacity-use-cases)
6. [Proposed approach](#6-proposed-approach)
   - 6.1 [Example logical models](#61-example-logical-models)
7. [Security considerations](#7-security-considerations)
8. [Summary of recommendations](#8-summary-of-recommendations)

---

## 1 Executive Summary

MUDDI – the Open Geospatial Consortium (OGC) Model for Underground Data Definition and Integration[^1] – defines a core and an extended Conceptual Model of feature classes that allows the integration of datasets from different types of information about the underground space, using different information models.

There are a number of established and emerging implementations of MUDDI in different countries and addressing different use cases.

It is proposed that a "Coordination and Capacity" use case for maintaining and extending utility networks would be a productive specialisation of the MUDDI model. This proposal is based on extensive evidence that the coordination of works is a priority area across different geographies, and that the knowledge and re-use of existing infrastructure capacity for the installation of new assets is an important driver of coordination, collaboration and operational efficiency.

Governments and regulators around the world see the benefits of works coordination in terms of cost-effectiveness and minimisation of disruption to citizens, and devote time and effort to defining incentives and regulations to encourage collaborative behaviour. There is also clear evidence that the knowledge of existing network capacity is a key contributor to coordination in supporting reuse of existing infrastructure. In addition, understanding existing and future network capacity is a key enabler for other infrastructure development.

While defining standards to consistently describe the information requirements for this area does not on its own unlock barriers to coordination and collaboration, such standards are critical when considering the need for consistent data exchange in different geographies and regulatory regimes, across sectors and between multiple organisations with different roles and priorities across different projects, and may contribute to an ecosystem of tools and processes that support the necessary data sharing and transparency that are enablers to effective coordination. Data standardisation will not solve this problem on its own, but the problem will not be solved comprehensively and at scale without data standards.

The problem statement is presented in **Section 3** and the evidence for action in **Section 4**.

A particular approach to this work is proposed. There is a significant gap between the definition of a Conceptual data model and the development of an implementation that conforms to that model. With little or no direction as to how a specific implementation may be developed, there may be little in common and weak interoperability between different independent implementations, even for a similar use case.

As a general approach to extending the MUDDI model or defining additional use cases, it is recommended that reference Logical Models should be developed and published to help fill this gap between concept and implementation and provide guidance and consistency for other implementers of the MUDDI model. The use cases outlined in this proposal provide a set for which Logical Models can be defined, and these may provide an exemplar and test case for this approach which may then be adopted for future developments.

Finally, there are likely to be particular sensitivities and security considerations around the representation of data supporting coordination and reuse of existing capacity. The availability of such information, and the appropriate level of detail, will likely be driven by the identity and role of the requestor, and the purpose for which they are requesting the data. Implementation of Coordination and Capacity use cases will therefore provide an opportunity to explore the representation of suitable attribution to support granular purpose-driven access control, and entities that allow the proper representation of the criteria to be used in granting or denying access, or modifying the response in terms of data scope and level of detail.

The following recommendations are made (see **Section 8**):

- To seek feedback on this paper and form a community of interest.
- To define in greater detail the use cases outlined in this paper.
- To design logical data models that serve the specified use cases.
- To include consideration of attribution relating to data sensitivity and security such that the data can form the basis for the implementation of granular access controls, based on user identity and context (including use case/purpose).
- To validate and test the logical models using representative data and expert review.
- To publish a test and validation report describing the use cases, logical data models and the results of the testing.
- Depending on the outputs of the validate and test phase, publish reference logical data models conforming to the MUDDI Conceptual Model, ideally via the MUDDI Standards Working Group.
- Develop recommendations for the applicability of this approach for future extensions and use cases for MUDDI for consideration by the MUDDI Standards Working Group.

---

## 2 Introduction

MUDDI – the Open Geospatial Consortium (OGC) Model for Underground Data Definition and Integration – defines a Conceptual Model of feature classes that allows the integration of datasets from different types of information about the underground space, using different information models. These may include models representing utility infrastructure, transport infrastructure, soils, ground water, or environmental parameters. The Conceptual Model is a superset of classes representing real-world objects that can be found in the subsurface. The MUDDI Conceptual Model was designed as a common basis to create Logical Models that make different types of subsurface data interoperable in support of a variety of use cases and in different jurisdictions and user communities.

There has been recent work to define an extension to the MUDDI Conceptual Model that more fully represents natural subsurface features and phenomena.

This paper argues that the highest-value next step is to model entities, attributes and relationships that represent:

- planned and future works that may impact buried infrastructure and the subsurface – such that risks and impacts may be assessed, and activities to coordinate works may be planned
- information that allows the current or future capacity of assets and networks to be calculated, estimated or inferred

It is proposed that the development and testing of reference logical data models will help to support several real-world use cases that would benefit from standardised information related to coordination and capacity.

### 2.1 Purpose

The purpose of this paper is to make the case for extending the MUDDI model in support of use cases in the Coordination and Capacity theme, and to stimulate discussion within the community of interest involved with street works, infrastructure planning and utilities. It sets out the problem, the supporting evidence and a high-level approach to progress the work. It is deliberately a discussion paper rather than a specification: it does not define a normative model or impose conformance requirements, but seeks the input needed to do so.

### 2.2 Why coordination and capacity?

This paper will argue that there is significant value in coordinating infrastructure works across multiple organisations and sectors, in terms of cost efficiency and reduction of disruption to citizens and businesses. Coordination of works is only possible if information about planned or future works is made available to those who may wish to collaborate on reducing duplication and disruption.

Another important way of enabling coordination is through the standard representation and controlled sharing of information about capacity – of individual assets and of utility, telecommunications and transport networks (see below).

There are various defined means and requirements for representing and sharing capacity information, and details of planned or future works in different sectors and for different use cases, but being able to link information that allows capacity to be calculated, estimated or inferred to physical locations and assets is often a gap that inter-operability with a model like MUDDI can help to overcome.

#### 2.2.1 What do we mean by capacity?

There are two main definitions of capacity that are relevant to this paper:

- The capacity for a specific asset to host or contain another asset. Examples may include the capacity of a streetlight to host telecommunications equipment or the capacity of a conduit (a duct or an abandoned pipe) to accommodate a cable or a sub-conduit.
- The current or future capacity of a telecommunications, utility or transport network to serve additional demand, for example arising from new housing development.

The main point to make from a data modelling point of view is that capacity is not a static characteristic of a network or an asset. The calculation of capacity may vary over time or according to the nature of the question being asked. It is important that data models intended to support questions of capacity represent the information required to calculate, estimate or infer capacity at a point in time or for a given scenario.

---

## 3 The problem: a UK perspective

While the details of the problem being addressed by this paper are provided from a UK perspective, based on the authors' direct experience, we believe that the problems outlined are global, and the evidence for action section contains evidence and examples from other parts of the world. We are grateful to those around the world who have contributed to that evidence, and we hope that this paper will help to bring together a global community of interest within which we can share further evidence for action.

Lack of coordination and collaboration between organisations, institutions, and sectors when carrying out street works and other works affecting subsurface and above ground infrastructure is a perennial problem. This is a repeated source of frustration for citizens[^2] whose lives and livelihoods are directly and indirectly affected by duplicate or unnecessary works arising from a lack of coordination and a lack of knowledge about existing infrastructure. Many of these issues are discussed at length in the UK Department for Transport's recent select committee on managing the impact of street works[^3].

In the UK, there are several schemes that incentivise or encourage the coordination of works[^4] [^5] [^6], but these often have a regional focus, despite many operators having a multi-region footprint, and outcomes are generally small scale[^7] [^8]. Current regulatory incentives, such as Ofgem's Collaborative Streetworks Output Delivery Incentive (ODI-F)[^9], usually focus on financial incentives with layers of governance often involved.

Despite current best efforts, why is collaboration still stubbornly low? An article written by the operators of Street Manager, England's national permitting system for street works, states that fewer than 1% of street works permits are marked as collaborative in the system[^10].

The article also talks about the behavioural nudges added to Street Manager to better enable collaboration via interventions at the permit issuance stage, and identifies 5 recurring blockers:

- **Lack of visibility.** Operators in one sector can't see what other sectors are planning.
- **Cognitive overload.** There is too much fragmented information to digest, inhibiting decisive action on collaboration.
- **Perceived lack of interest in collaboration.** There is a sense that other parties won't engage anyway.
- **Ineffective communication.** The right information doesn't reach the right people at the right time.
- **Liability concerns.** Sharing data or coordinating work is seen as a legal or security risk.

To add to this, different sectors answer to different regulators on different timescales, such as Ofgem's RIIO framework (for energy) and Ofwat's AMP framework (for water and wastewater). Regulatory periods often drive the requirements for programmes of work that could be channels for collaboration, such as the iron mains risk reduction programme mandated by the Health and Safety Executive, carried out by the UK Gas Distribution companies, all within the context of Ofgem's RIIO framework[^11] [^12].

As well as a lack of coordination of works, ambitious targets for housebuilding in the UK are hampered partly by a lack of knowledge about the current or future capacity of utility networks to support new or enlarged populations. This leads to uncertainty which can impact investor confidence and delay the planning process[^13].

According to the Home Builders Federation (HBF) reporting in September 2025[^14]:

> "…almost 30,000 new homes were blocked at that time, including 7,000 Affordable Homes, due to supposed concerns over inadequate wastewater infrastructure, exacerbating the housing crisis".

Additionally, in London, house building has been impacted by a lack of sufficient electricity supply due to data centres[^15].

Questions of demand and network capacity are clearly nuanced and complex but being able to consistently report on and estimate indicative current and future capacity at a location will help to fill what is clearly a significant gap between those concerned with expanding demand and those responsible for supply.

Technology and innovation are seen as key to transforming and streamlining the planning process, but progress will be severely hampered by the absence of available and good quality data in a standard form that is maintained, governed, and has an active community willing to support it into the future.

A standardised way of describing and sharing information at scale across sectors and regions about future utility works and existing / future capacity in networks will not solve these issues on its own, but they will not be solved comprehensively and at scale without this foundation.

Standards make it easier for service providers and innovators to build the tools and services that support collaboration, and to enable better adoption of the incentive schemes that already exist. It may also allow organisations to align much earlier, well before permits are even planned or raised. Rather than nudging behaviour at the point of permitting, a shared standard lets sectors see and respond to each other's plans much earlier in planning processes. Developers could also benefit from knowing well in advance both current and future planned network capacity in an area.

The principle is simple: define once, share many times securely with those who need the information.

---

## 4 Evidence for action

Besides the reflections in the previous section on the evidence for the relatively small-scale adoption of incentives to encourage coordination and collaboration, the need for coordination and availability of usable capacity information is clearly demonstrated by the legislative measures and regulations introduced worldwide to mandate or incentivise this behaviour.

In the UK there is a track record of using data standards to enable the provisions set out in the New Roads and Street Works Act, 1991 (NRSWA)[^16], improving how we manage street and road works:

- The standards-based National Underground Asset Register (NUAR) improves how undertakers fulfil provisions such as NRSWA section 79 centred on the recording and location of apparatus and NRSWA section 80 centred on the duty to inform others of the location of apparatus. Evidence of this can be found in the NRSWA amendments made in part 3 of the Data Use and Access Act[^17].
- The National Streets Gazetteer, and the BS7666 standard it implements, with its Unique Street Reference Numbers (USRNs), was defined as an essential data source to support many provisions laid out in the NRSWA legislation[^18]. Section 53 is particularly important as it relates to the provision of a street works register. Concrete evidence of this can be found in SI 2007/1951 Reg.4(3)[^19] where BS7666 is directly mentioned as the standard to be respected when referencing streets.

NRSWA also provides a legal basis for street works coordination:

- Section 59: street authorities must use best endeavours to co-ordinate street works of all kinds in their area.
- Section 60: undertakers must use best endeavours to co-operate with the street authority and with each other.

Recommendation 9 from the UK Department for Transport's recent select committee on managing the impact of street works focused on the difficulties of collaboration and how future work plans are shared. The UK government's response acknowledged this, citing that:

- Sharing forward planning information on Street Manager is encouraged, not mandatory.
- The non-mandatory status stems from reliance on voluntary cooperation and commercial sensitivity.
- Broadband/telco operators are particularly reluctant as forward plans could disclose expansion plans to competitors.
- Forward plans are inherently unstable as funding cycles, customer demand, and planning approvals cause frequent change.

An approved, standardised form for exchanging forward works plans could help to address commercial sensitivities and the dynamic, changing nature of plans. NUAR is a successful example of a similar intervention in the same sector. It proved that sensitive infrastructure data can be collected and shared at scale, with access controls that satisfy commercial and security concerns.

The use cases and recommendations laid out in this paper continue the trend of data standards supporting legislation and could help local authorities and utilities companies to fulfil NRSWA sections 59 and 60.

The need for coordination and availability of usable capacity information is also exemplified by the EU Gigabit Infrastructure Act[^20] which entered into force in May 2024. While this regulation is focused specifically on the efficient deployment of very-high-capacity telecoms networks (VHCNs), it articulates the need generally for coordination and transparency on civil works to improve the speed and efficiency of infrastructure deployment. Public bodies are required under the Act to ensure greater transparency and coordination regarding public works projects such as roadworks, and gas or water pipe upgrades). Furthermore, when public bodies plan civil works, they must actively provide telecom operators with the opportunity to co-deploy fiber-optic cable or 5G equipment at the same time. There is no specific data standard defined in the Act for representing planned works or conduit capacity.

Clear evidence that advertising reusable capacity can accelerate broadband deployment can be gathered from the UK full-fibre rollout programme. Ofcom (the UK's telecoms regulator) implemented the Physical Infrastructure Access (PIA) approach, requiring BT Openreach to make its ducts and poles available to competitors at cost-based prices. Under this regime, full-fibre coverage rose from around 24% of premises (around 6.9 million) in 2021 to roughly 78% (about 23.7 million) by 2025, with around 169 operators using the shared infrastructure[^21].

There are commercial offerings in the UK market and elsewhere seeking to solve the problem of advertising (and monetising) existing capacity particularly for installation of telecoms infrastructure. The development and adoption of data standards in this space should be complementary to these offerings and indeed should help commercial providers to address broader markets and other geographies using a standardised approach.

Also in the telecoms domain, work was carried out in the UK in 2022 on the Digital Connectivity Infrastructure Accelerator (DCIA) programme[^22] concerned with the use of existing street furniture for the efficient and cost-effective deployment of 5G network infrastructure. This resulted in the publication of a specification of data requirements in 2023 - PAS190:2023[^23] - which may form a useful basis of such information requirements in other regions.

The Riyadh Infrastructure Projects Center (RIPC) in the Riyadh region of Saudi Arabia manages infrastructure works across more than 26 service providers from 6 sectors, with historically no shared view of planned or active works. RIPC's Integrated Infrastructure Coordination Plan (IICP) was established to address this directly, highlighting the importance and priority of coordination. To date, the platform has processed over 8,000 projects, resolving more than 8,500 spatial conflicts and more than 80,000 temporal conflicts, delivering significant cost savings on reduced excavations and reduced disruption costs.

RIPC have two distinct operational phases for coordination interventions:

- **Phase 1: Planning Coordination**: Before projects are approved, RIPC runs a coordination cycle that cross-references all planned works spatially and temporally, identifying conflicts and consolidation opportunities across entities.
- **Phase 2: Permit Issuance Coordination**: A second coordination cycle sits within the permit issuance process, ensuring no excavation permit is granted without validation against active and planned works in the same corridor.

This multi-phase intervention approach informs the thinking on some of the proposed use cases described below.

The primary cost of installing subsurface infrastructure is for excavation and reinstatement. The US Federal Highway Administration estimates that roughly 90% of the cost of deploying broadband arises where the work requires significant excavation of the roadway, such that coordinating installation with other works can make public funding many times more effective[^24].

The inference is that installing a conduit once and subsequently sharing it avoids the largest cost component for every subsequent party, particularly if existing infrastructure spans waterways or significant highways. San Francisco's "Trench Once" specification illustrates the potential cost saving: the cost of installing a new conduit is estimated to be around $128,000 per street mile, compared to a cost of around $71,000 for re-use of an existing conduit[^25]. These cost-reduction opportunities are not achievable unless planned works and available trenches or ducts are "advertised" in advance: a works promoter can only join an open trench, or reuse a spare duct, if they know the trench or duct exists, is available and has sufficient spare capacity.

The benefits of "good quality, standardised, usable network capacity data"[^26] have also been articulated for energy networks by Ofgem, the UK energy regulator. Ofgem have mandated a requirement for electricity networks to deliver standardised capacity data using a sector-specific Common Information Model[^27]. This however is distinct from the model of physical assets embodied by MUDDI, which may hamper the ability for this information to support location-specific projects. A simplified mapping from the network analysis and planning domain to the domain of physical networks and assets will therefore be of value.

Add to this the economic case published for the NUAR in the UK[^28] which included references to efficiency improvements for works to maintain buried assets arising from ready access to standardised data, the anecdotal evidence of public frustration with the perceived lack of coordination of street works referenced previously, and the requirement of property tech innovators to access network capacity data to streamline the planning process[^29], there is significant evidence that access to standardised information about planned and future works, and existing or planned capacity – of networks and of assets – would be valuable for multiple use cases.

---

## 5 Use cases

### 5.1 Coordination use cases

Coordination may be considered to potentially require interventions in two distinct operational phases:

- **Phase 1: Forward Planning.** Long-term and strategic plans from different organisations and different sectors may provide a chance to spot opportunities for coordination in the future, which may provide an opportunity to update plans to take advantage of collaboration opportunities which may reduce costs for all parties.
- **Phase 2: Works Planning**: At the stage where plans for specific works are solidified, with dates assigned and permits issued, there may be opportunities for tactical collaboration, and also for risk assessment and potential interventions by asset owners whose networks may be affected by planned works.

On that basis, two distinct, but related, use cases and logical models are proposed:

- **Long term planning.** Standardised information about long term network extension and hardening plans supports consistency in local and regional infrastructure plans across different regions and allows utilities to make strategic assessments of collaboration opportunities.
- **Notification of planned works.** A standard representation of works at different stages of planning allows information to be provided in a consistent way to those who may wish to intervene as part of asset protection processes, or those who may wish to collaborate tactically on co-located works. An open standard describing planned works may allow new entrants and innovators to develop new approaches to mitigating third party damage.

### 5.2 Capacity use cases

- **Duct capacity.** Supporting attribution that allows duct capacity to be calculated or estimated may help to support the "Dig Once" approach and encourage the cost-effective re-use of existing infrastructure. Those organisations with spare duct capacity may be able to monetise this availability, and a standard representation helps to support innovation in this space.
- **Availability of abandoned pipes.** Abandoned pipes may serve as conduits for telecoms and other cables, and a clear and standard representation of these assets can help to surface opportunities for reuse and repurposing.
- **Existing street furniture for telecommunications equipment.** The data requirements for determining the suitability of lighting columns and other street furniture for supporting telecoms infrastructure is well described, and including such attribution in a MUDDI-conformant model may improve inter-operability and adoption of these data standards.
- **Estimation of existing or planned network capacity.** Uncertainty about the current and future capacity of networks (particularly electricity, water and sewer networks) impacts confidence and investment in new housing. A standard representation of attribution that would allow such capacity to be estimated at a time and location will improve coordination between planning authorities and network operators and may help to remove a barrier to innovation in the prop tech space.

---

## 6 Proposed approach

It is proposed that a use case driven approach will be taken in order to define, develop and test candidate logical models – inheriting from and conforming to the MUDDI Core and Extended Conceptual Models – that may represent the information requirements of the use cases outlined above.

These logical models may need some specialised input, particularly around calculating network capacity.

A programme of validating and testing these logical models using representative data and expert review will be required to establish the validity and value of the approach.

Recommendations to the MUDDI SWG for extensions to the MUDDI Conceptual Model may arise if there are entities and attributes in the new logical models which are deemed to be of sufficiently general and universal applicability. This can only be established once the logical models have been developed and validated.

It is proposed that a successful outcome could be the development and publication of a number of validated reference logical models covering the coordination and capacity use cases, regardless of whether extensions to the Conceptual Model are recommended.

### 6.1 Example logical models

This section includes examples of MUDDI-conformant logical models which may support the use cases outlined above:

- **Planned works and future plans.** Feature types for "Future Plans" and "Proposed Work" with "Proposed Work" inheriting from "Future Plans" and providing a greater level of detail. Proposed Work instances should also be relatable (many-to-one) to a Future Plans instance to indicate the progress of future plans to planned work. The attribution of the Proposed Work specialisation may be based on the published draft specification for the "Proposed Works Enquiry" API on the NUAR GitHub[^30].
- **Duct capacity.** A "Duct" specialisation of the NetworkAccessory::Container Feature Type will be required for the representation of attribution that allows spare duct capacity to be estimated. The dimensions of the duct will be required as well as details of existing cables within the duct (possibly aggregated into an overall area value) and the maximum allowed fill factor for the duct as a percentage.
- **Abandoned pipes.** A specialisation of the NetworkLink Feature Type will be required to represent pipes with an "Abandoned" status, and include information such as diameter, depth, material and other characteristics relevant for re-use as a conduit. Specialisations for NetworkNode or NetworkAccessory::Access may also be required to identify likely ingress points.
- **Street furniture capacity.** Specialisations of the NetworkNode Feature Type will likely be required to represent lighting columns and other street furniture. The information requirements for establishing suitability to host telecoms equipment are defined in PAS190:2023[^31] and the attributes of the specialised Feature Type should reflect this specification.
- **Electricity network capacity.** A specialisation of the NetworkNode (and/or possibly Site) Feature Type (or a new abstract Feature Type) will be required to represent Substations, and these should be related to the Network Feature Type representing whole or partial networks. Some specialist knowledge and research will be required to establish desirable and feasible attribution at the substation level to allow the estimation of capacity. Feature Types representing future capacity in terms of contracted future connections and time-based load profile data may also be required as entities related to the Substation specialisation.
- **Water network capacity.** Specialisations of NetworkLink and NetworkNode will be required to represent the diameters, material and material properties of pipes, and node elevations (for gravity-fed sewers) and pumping stations for water networks. Some specialist knowledge and research will be required to establish desirable and feasible attribution for the estimation of spare capacity which can be aggregated to the network level via relationships with the Network Feature Type.

---

## 7 Security considerations

Aspects of the information described in this document, relating to planned works and capacity are likely to be considered sensitive by some sectors and organisations. While the design and implementation of the logical data models described in this paper may be relatively straightforward, their future adoption may be hampered by issues or security and reluctance to share such data.

NUAR has demonstrated that good data model design can contribute to secure data sharing by modelling at a granular level information that can be used to implement effective access control.

It is proposed that a strand of this proposed work should be dedicated to modelling characteristics relating to data sensitivity and security, such that data providers and national agencies would be able to model information supporting granular access control.

In particular It is proposed that development of logical models for coordination and capacity may present an opportunity to develop models for purpose-driven access control, such that user identity and context (user role, organisation, use case/purpose, location and extent, and data requirements) may be modelled and attribution at the feature or (subordinate) network level may dictate which user types and contexts are allowable. This may help to develop models (or Building Blocks) that support implementers in solving a universal and recurring problem around secure access to subsurface data.

---

## 8 Summary of recommendations

- To seek feedback on this paper and form a community of interest.
- To define in greater detail the use cases outlined in this paper.
- To design logical data models that serve the specified use cases.
- To include consideration of attribution relating to data sensitivity and security such that the data can form the basis for the implementation of granular access controls, based on user identity and context (including use case/purpose).
- To validate and test the logical models using representative data and expert review.
- To publish a test and validation report describing the use cases, logical data models and the results of the testing.
- Depending on the outputs of the validate and test phase, publish reference logical data models conforming to the MUDDI Conceptual Model, ideally via the MUDDI Standards Working Group.
- Develop recommendations for the applicability of this approach for future extensions and use cases for MUDDI for consideration by the MUDDI Standards Working Group.

---

## Footnotes

[^1]: <https://www.ogc.org/standards/muddi/>

[^2]: "The Roads Remember: Permits, people, and pet shops", blog, <https://www.ccarlon.dev/blog/street_works/>

[^3]: <https://committees.parliament.uk/work/8705/managing-the-impact-of-street-works/publications/>

[^4]: <https://www.ofwat.gov.uk/wp-content/uploads/2025/03/Streetworks-Collaboration.pdf>

[^5]: <https://www.ofwat.gov.uk/wp-content/uploads/2024/12/TMS-Streetworks-collaboration-_-third-party-material.pdf>

[^6]: <https://www.london.gov.uk/programmes-strategies/better-infrastructure/infrastructure-coordination/streets-service>

[^7]: <https://smarter.energynetworks.org/collaborative-streetworks/?dateType=start&query>

[^8]: <https://www.igem.org.uk/future-energy-networks/publications.html?sortBy=recent&information_type=collaborative-streetworks>

[^9]: <https://www.ofgem.gov.uk/sites/default/files/2026-03/collaborative-streetworks-governance-document.pdf>

[^10]: <https://medium.com/kainosxd/applying-behavioural-science-to-roadworks-disruption-designing-for-collaboration-in-street-manager-68cbf08476ce>

[^11]: <https://www.hse.gov.uk/gas/supply/mainsreplacement/enforcement-policy-2026-2031.htm>

[^12]: <https://sgn.co.uk/sites/default/files/media-entities/documents/2024-12/SGN-GD3-EJP-RPX-005-Tier-1-Mains-and-Services-Final-Version-1.0-Publish.pdf>

[^13]: <https://geovation.uk/wp-content/uploads/2025/07/Challenge-Deep-Dive-Report-V2-20250701.pdf>

[^14]: <https://www.hbf.co.uk/news/drain-nation-release/>

[^15]: <https://www.bbc.co.uk/news/articles/c0mpr1mvwj3o>

[^16]: <https://www.legislation.gov.uk/ukpga/1991/22/contents>

[^17]: <https://www.legislation.gov.uk/ukpga/2025/18/part/3>

[^18]: <https://www.geoplace.co.uk/press/2006/nsg-confirmed-as-the-required-data-source-for-notification-of-street-works>

[^19]: <https://www.legislation.gov.uk/uksi/2007/1951/regulation/4/made>

[^20]: <https://eur-lex.europa.eu/EN/legal-content/summary/gigabit-infrastructure-act-gia.html>

[^21]: <https://bratby.law/ofcom-telecoms-access-review-2026-31/>

[^22]: <https://www.gov.uk/guidance/digital-connectivity-infrastructure-accelerator-programme>

[^23]: <https://www.bsigroup.com/en-GB/insights-and-media/insights/brochures/pas-190-assessment-of-lighting-and-cctv-columns-for-multi-functional-use/>

[^24]: <https://www.fhwa.dot.gov/policy/otps/policy_brief_dig_once.pdf>

[^25]: <https://www.tellusventure.com/downloads/bank/ctc_dig_once_spec_ccsf_apr2015.pdf>

[^26]: <https://www.ofgem.gov.uk/sites/default/files/2025-12/connections-end-to-end-review-next-steps-final.pdf>

[^27]: <https://commercial.nationalgrid.co.uk/our-network/energy-data-hub/common-information-model>

[^28]: <https://www.gov.uk/government/publications/national-underground-asset-register-unlocking-value-for-industry-and-the-wider-economy/national-underground-asset-register-nuar-economic-case-summary>

[^29]: <https://geovation.uk/wp-content/uploads/2025/07/Challenge-Deep-Dive-Report-V2-20250701.pdf>

[^30]: <https://github.com/national-underground-asset-register/nuar-enquiry-api-spec>

[^31]: <https://www.bsigroup.com/en-GB/insights-and-media/insights/brochures/pas-190-assessment-of-lighting-and-cctv-columns-for-multi-functional-use/>
