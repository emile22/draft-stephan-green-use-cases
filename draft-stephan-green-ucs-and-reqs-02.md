---
title: "Requirements for Energy Efficiency Management"
abbrev: "Requirements for Energy Efficiency"
docname: draft-stephan-green-ucs-and-reqs-02
category: info
stand_alone: true

submissiontype: IETF  # also: "independent", "editorial", "IAB", or "IRTF"
consensus: true

area: "Operations and Management"
workgroup: "Getting Ready for Energy-Efficient Networking"
keyword: Sustainability, Ressources

venue:
  group: "Getting Ready for Energy-Efficient Networking"
  type: "Working Group"
  mail: "green@ietf.org"
  arch: "https://mailarchive.ietf.org/arch/browse/green/"
  github: "emile22/draft-stephan-green-ucs-and-reqs"
  latest: "https://emile22.github.io/draft-stephan-green-ucs-and-reqs/draft-stephan-green-ucs-and-reqs.html"

v: 3

author:

  -
    fullname: Emile Stephan
    org: Orange
    email: emile.stephan@orange.com
  -
    fullname: Marisol Palmero
    org: Cisco Systems, Inc.
    email: mpalmero@cisco.com
  -
    fullname: Benoit Claise
    org: Huawei
    email: benoit.claise@huawei.com
  -
    fullname: Qin Wu
    org: Huawei
    email: bill.wu@huawei.com
  -
    fullname: Luis M. Contreras
    org: Telefonica
    email: luismiguel.contrerasmurillo@telefonica.com

normative:

informative:

  operators-inputs:
    title: "Input from Operators to GREEN BoF"
    date: 2024-07-20
    target: "https://datatracker.ietf.org/meeting/120/materials/slides-120-green-input-from-operators-to-green-bof-01"

  GREEN-BOF:
    title: "BOF proposal for GREEN WG Creation"
    date: 2024-05-10
    target: "https://github.com/marisolpalmero/GREEN-bof"

  green-bof-reqs:
    title: "Green BoF requirements collections"
    date: 2024-09-03
    target: "https://datatracker.ietf.org/doc/draft-stephan-green-bof-reqs-collections"

  rfc6988bis-green:
    title: "Requirements for Energy Efficiency Management, 11 years after the EMAN RFC6988"
    date: 2024-07-21
    target: "https://datatracker.ietf.org/doc/draft-eman-green-rfc6988bis"

  sustainability-insights:
    title: "Sustainability Insights"
    date: 2024-05-07
    target: "https://datatracker.ietf.org/doc/html/draft-almprs-sustainability-insights"

  legacy-path:
    title: "Requirements for Energy Efficiency Management"
    date: 2024-07-21
    target: "https://datatracker.ietf.org/doc/draft-stephan-legacy-path-eco-design"

  TS23.501:
    title: "3GPP TS 23.501, System architecture for the 5G System (5GS), 17.6.0."
    date: 2022-09-22

  TS28.554:
    title: "3GPP TS 28.554, Management and orchestration; 5G end to end Key Performance Indicators (KPI), 17.15.0."
    date: 2024-09-25

  ONF-MW:
    title: "ONF TR-532, Microwave Information Model, version 2.0."
    date: 2024-01-31

  mWT025:
    title: "ETSI GR mWT 025, Wireless Backhaul Network and Services Automation: SDN SBI YANG models, V1.1.1."
    date: 2021-03-31

  GREEN_NGNM:
    title: "NGMN Alliance, GREEN FUTURE NETWORKS: METERING IN VIRTUALISED RAN INFRASTRUCTURE"
    target: "https://www.ngmn.org/publications/metering-in-virtualised-ran-infrastructure.html"

  UC_Interim18Dec24:
    title: "UC_Requirements_GREENWG_v4"
    target: "https://datatracker.ietf.org/meeting/interim-2024-green-01/materials/slides-interim-2024-green-01-sessa-uses-cases-requirements-presentation-01"


--- abstract

This document delineates the requirements for standards specifications in Energy Efficiency Management, extending the foundational work of RFC6988 and incorporating recent insights from operator requirements and the GREEN BoF discussions. Eleven years after the publication of RFC6988, this document reassesses and updates the requirements to align with contemporary needs.

The primary objectives of this draft, which are listed in the goals and scope with the creation of the GREEN WG charter, is focusing on two main targets:
(1) collecting and updating requirements for the management of energy-efficient networks, and
(2) defining use cases for managing energy-efficient networks.

This draft merges the drafts [rfc6988bis-green] and [green-bof-reqs].

Discussion Venues

Source of this draft and an issue tracker can be found at https://github.com/emile22/draft-stephan-green-terms-ucs-and-reqs


--- middle

# Introduction

This document delineates the requirements for standards specifications in Energy Efficiency Management, extending the foundational work of RFC6988 and incorporating recent insights from operator requirements and the GREEN BoF discussions. Eleven years after the publication of RFC6988, this document reassesses and updates the requirements to align with contemporary needs.

The primary objectives of this draft, which are listed in the goals and scope with the creation of the GREEN WG charter, is focusing on two main targets:
(1) collecting and updating requirements for the management of energy-efficient networks, and
(2) defining use cases for managing energy-efficient networks.

This draft replaces the drafts [rfc6988bis-green] and [green-bof-reqs] and groups requirements from the documents of the GREEN WG proponents [charter-refinement], [operators-inputs], [GREEN-BOF], [sustainability-insights], [legacy-path] and [rfc6988bis-green]. The aim is to determine initial sets of requirements actionable at different levels of the framework presented below {{framework}}.

Requirements are named and grouped in tables and are set with individual priority (to be) determined by the GREEN WG consensus.

Section 2 groups the 'core' use cases. Several of them might not be relevant for the current charter.

Section 3 recalls a set of requirements established after the BoF in [charter-refinement].

Section 4 recalls [rfc6988bis-green] requirements which may fit to the GREEN WG. They still have to be grouped in tables and set with individual priorities.

Section 5 recalls the raw framework discussed during the BoF to illustrate the segmentation of the requirements in three core functions: discovery, monitoring, and control. Discovery functions involve identifying energy-managed networks, devices, and their components, as well as discovering the inventory of power components capabilities, optimization control capabilities, and nominal condition use. Monitoring functions encompass tracking power states, power attributes, energy consumption, network performance, and energy efficiency metrics. Control functions include managing energy-saving and optimization functions and the power states of energy-managed devices and their components.

Terms and definitions, mostly  from RFC6988, related to energy efficiency metrics are recalled in Appendix and will be discussed in later stages for potential integration in another GREEN WG document.

## Background

   With rising energy costs and an increasing awareness of the
   environmental impact of running information technology equipment, Energy
   efficiency Management functions and management interfaces are becoming
   an additional basic requirement for network management systems and devices
   connected to a network.

   This document defines requirements for standards specifications for
   Energy efficiency Management, including discovery functions, monitoring functions
   and control functions.
   Energy efficiency Management functions focus mainly on network devices and
   their built-in components that receive and provide electrical energy.  Devices such
   as switches, routers, servers and storage devices should have an IP address providing a
   management interface for the network device. Alternatively, energy-related devices (for
   example, in building management, which typically don't support IP) might be connected
   via a proxy/gateway with an IP address.

   These requirements are concerned with the standards specification
   process and not the implementation of specified standards.  All
   requirements in this document must be reflected by standards
   specifications to be developed.  However, which of the features
   specified by these standards will be mandatory, recommended, or
   optional for compliant implementations is to be defined by Standards
   Track document(s) and not in this document.

# Use Cases

This section describes a number of relevant use cases with the purpose of elicit requirements for Energy Efficiency Management.
This is a work in progress and additional use cases will be documented in next versions of this document. Use cases which are not tied enough to the current GREEN chater will be moved to the GREEN WG wiki pages or to other WGs or RGs.

## Incremental Application of the GREEN Framework {#incremental-use-case}

This section describes an incremental example [legacy-path] of usage showing how a product, a service and a network can use the framework in different settings.

This use case is the less trendy of all the use cases by far as its ambitious is limited to migration and coexistence, as usual. Nevertheless from a telco perspective, it is the centrality for 2 main reasons:

- to start immediatly the move to energy efficiency using legacy devices;
- to account the gain of the move one started;

Once upon a time there was an very old legacy router named Rusty equipped with outdated ethernet and ugly optical interfaces. Despite his worn-out appearance, Rusty was determined to contribute to the energy efficiency effort. He dreamed of finding a way to optimize his old circuits and help reduce the power consumption of the network he had faithfully served for so many years. Though he was no longer in his prime, Rusty believed that even an old router like him could make a difference in a world striving for sustainability and help reduce the carbon footprint. He is convince that he still had a part to play in making the digital world a greener place.

Device moving gradually to GREEN energy efficiency support:

- step 1 "baseline" : establishing a reference point of typical energy usage, which is crucial for identifying inefficiencies and measuring improvements over time.
  At this step the controler use only the (c) part of the framework. It is collected from the datasheet.

By establishing a baseline and using benchmarking, you can determine if your networking equipment is performing normally or if it is "off" from expected performance, guiding you in making necessary improvements.

The initial measurement of your networking equipment's energy efficiency and performance, aka Baselining, needs to be in coordination with the vendor specifications and industry standards to understand what is considered normal or optimal performance.
example:
Baseline: Your switches operate at 5 Gbps per watt.
Benchmarking: Vendor specification is 8 Gbps per watt; industry standard is 10 Gbps per watt.
Action: Implement energy-saving measures and upgrades.
Tracking: Measure again to see if efficiency improves towards 8-10 Gbps per watt.

- step 2 "component":  part of the device hw or sw migrated to support GREEN framework elements.

- step 3 "device controleur"

- step 4 "network level"

For this use case, the following requirements apply :

|id|category|requirements|note|Pri|
|:----|:----|:----|:----|:----|
|Req01-UCINC|Discovery|Component granularity, e.g., per line-card, per-port|Per component |1|
|Req02-UCINC|Observability|Availability of information on the power consumption of the device, without needing instrumentation connected to the infrastructure|Related to connected device case|1|
|Req03-UCINC|Analysis|Common definition of energy efficiency in network devices/components|Standard metric|1|
|Req04-UCINC|Inventory Management|component control capacity (aka component max power-on/power-off frequency supported)|Per component control| 1 (i)|
|Req05-UCINC|Analysis|assess the gains of introducing eco-designed components in a device|Device Level Mgmt| 1 (ii)|
|Req06-UCINC|Control& Mgmt|comprehensive support of network-wide energy efficiency includes legacy devices|Network Level Mgmt| 1 (iii)|

(i) Avoid a power-on/power-off frequency to break component parts (aka laser, power parts, wire connectors ...)

(ii) the gain must be measurable

(iii) network-wide  energy efficiency solutions must include legacy devices and green-wg ready devices

## Selective reduction of energy consumption in network parts proportional to traffic levels

Traffic levels in a network follow patterns reflecting the behavior of consumers. Those patterns show periodicity in the terms of the traffic delivered, that can range from daily (from 00:00 to 23:59) to seasonal (e.g., winter to summer), showing peaks and valleys that could be exploited to reduce the consumption of energy in the network proportionally, in case the underlying network elements incorporate such capabilities. The reduction of energy consumption could be performed by leveraging on sleep modes in components up to more extreme actions such as switching off network components or modules. Such decisions are expected to no impact on the service delivered to customers, and could be accompanied by traffic relocation and / or concentration in the network.
For this use case, the following requirements apply:

|id|category|requirements|note|Pri|
|:----|:----|:----|:----|:----|
|Req01-UCRED|Observability|Component granularity, e.g., per line-card, per-port|Per component measurement|1|
|Req02-UCRED|Observability|Availability of information on the power consumption of the device, without needing instrumentation connected to the infrastructure|Related to connected device case|1|
|Req03-UCRED|Analysis|Common definition of energy efficiency in network devices/components|Standard metric|1|
|Req04-UCRED|Analysis|Ability of multi-layer analysis (e.g., IP plus optical)|POI Use Case|3|
|Req05-UCRED|Control& Mgmt|To have devices with elastic power consumption according to the carried traffic|Dynamic Energy Saving|2|
|Req06-UCRED|Control& Mgmt|Advanced sleep mode, needing some sort of low power mode when node is lightly utilized|Dynamic Energy Saving|2|
|Req07-UCRED|Control& Mgmt|Ability to steer traffic based on power savings|Traffic Engineering|4|

## Reporting on Lifecycle Management

   Lifecycle information related to manufacturing energy costs, transport,
   recyclability, and end-of-life disposal impacts is part of what is
   called "embedded carbon." This information is considered to be an
   estimated value, which might not be implemented today in the network
   devices. It might be part of the vendor information, and to be collected
   from datasheets or databases. In accordance with ISO 14040/44, this
   information should be considered as part of the sustainable strategy
   related to energy efficiency. Also, refer to the ecodesign framework
   [(EU) 2024/1781] published in June by the European Commission.

### Carbon Reporting

   To report on carbon equivalents for global reporting, it is important
   to correlate the location where the specific entity/network element
   is operating with the corresponding carbon factor. Refer to the world
   emission factor from the International Energy Agency (IEA), electricity
   maps applications that reflect the carbon intensity of the electricity
   consumed, etc.

### Energy Mix

Energy efficiency is not limited to reducing the energy consumption, it is common to include carbon free, solar energy, wind energy, cogeneration in the efficiency.

The type of the sources of energy of the power is one criteria of efficiency.

There are other dimensions that must visible: As many telecom locations include battery or additionnally several backups levels (as example battery, standby generator ...) there is a requirement to known exactly when a backup power is in used and which one is.

## Real-time Energy Metering of Virtualised or Cloud-native Network Functions

Facilitating more precise and real-time estimations of energy consumed by virtualised or cloud-native network functions.

Effective metering of virtualized network infrastructure is critical for the efficient management and operation of next-generation mobile networks [GREEN_NGNM].

## Indirect Energy Monitoring and control

   While the conventional requirements summarized above seem to be all
   that would be needed for Energy Management, there are significant
   differences between Energy Management and most well-known network
   management functions.  The most significant difference is the need
   for some devices to report on other entities.  There are two major
   reasons for this.

   o  For monitoring a particular entity, it is not always sufficient to
      communicate only with that entity.  When the entity has no
      instrumentation for determining power, it might still be possible
      to obtain power values for the entity via communication with other
      entities in its power distribution tree.  A simple example of this
      would be the retrieval of power values from a power meter at the
      power line into the entity.  A Power Distribution Unit (PDU) and a
      Power over Ethernet (PoE) switch are common examples.  Both supply
      power to other entities at sockets or ports, respectively, and are
      often instrumented to measure power per socket or port. Also it
      could be considered to obtain power values for the entity via
      communication with other entities outside of the power distribution
      tree, like for example external databases or even data sheets.

   o  Similar considerations apply to controlling the power supply of an
      entity that often needs direct or indirect communications with
      another entity upstream in the power distribution tree.  Again, a
      PDU and a PoE switch are common examples, if they have the
      capability to switch power on or off at their sockets or ports,
      respectively.

   These specific issues of Energy Management, as well as other issues,
   are covered by requirements specified in Sections 7 and 8.

   The requirements in these sections need a new Energy Management
   framework that deals with the specific nature of Energy Management.
   The actual standards documents, such as MIB module specifications,
   address conformance by specifying which features must, should, or may
   be implemented by compliant implementations.

## Consideration of other domains for obtention of end-to-end metrics

The technologies under the scope of IETF provide the necessary connectivity to other technological domains. For the obtention of metrics end-to-end it would be required to combine or compose the metrics per each of those domains.

An exemplary case is the one of a network slice service. The concept of network slice was initially defined by 3GPP {{TS23.501}}, and it has been further extended to the concerns of IETF {{?RFC9543}}.

In regards energy efficiency, 3GPP defines a number of energy-related key performance indicators (KPI) in {{TS28.554}}, specifically Energy Efficiency (EE) and Energy Consumption (EC) KPIs. There are KPIs particular for a slice supporting a specific kind of service (e.g., Mobile Broadband or MBB), or generic ones, like Generic Network Slice EE or Network Slice EC. Assuming these as the KPIs of interest, the motivation of this use case is the obtention of the equivalent KPIs at IETF level, that is, for the network slice service as defined in {{?RFC9543}}.

Note that according to {{TS28.554}}, the Generic Network Slice EE is the performance of the network slice divided by the Network Slice EC. Same approach can be followed at IETF level. Note that for avoiding double counting the energy at IETF level in the calculation of the end-to-end metric, the 3GPP metric should only consider the efficiency and consumption of the 3GPP-related technologies.

## Dynamic adjustment of network element throughput according to traffic levels in wireless transport networks

Radio base stations are typically connected to the backbone network by means of fiber or wireless transport (e.g., microwave) technologies. In the specific case of wireless transport, automation frameworks have been defined {{ONF-MW}}{{?RFC8432}}{{mWT025}} for their control and management.

One of the parameters subject of automated control is the power of the radio links. The relevance of that capability is that the power can be adjusted accordingly to the traffic observed. Wireless transport networks are typically planned to support the maximum traffic capacity in their area of aggregation, that is, the traffic peak. With that input, the number of radio links in the network element and the corresponding power per radio link (for supporting a given modulation and link length in the worst weather conditions) are configured. This is done to avoid any kind of traffic loss in the worst operational situation. However, such operational needs are sporadic, giving room for optimization during normal operational circumstances and/or low traffic periods.

Power-related parameters are for instance defined in {{?RFC8561}}. Those power parameters can be dynamically configured to adjust the power to the observed traffic levels with some coarse granularity, but pursuing certain degrees of proportionality.

## Video streaming use case

Video streaming is nowadays the major source of traffic observed in ISP networks, in a propotion of 70% or even higher. Over-the-top distribution of streaming traffic is typically done by delivering a unicast flow per end user for the content of its interest.In consequence, during the hours of higher demand, the total traffic in the network is proportional to the concurrence of users consuming the video streaming service. The amount of traffic is also dependent of the resolution of the encoded video (the higher the resolution, the higher the bit rate per video flow), which tends to be higher as long as the users devices support such higher resolutions.

The consequence of both the growth in the number of flows to be supported simultaneously, and the higher bit rate per flow, is that the nework elements in the path between the source of the video and the user have to be dimensioned accordingly. This implies the continuous upgrade of those network elements in terms of capacity, with the need of deploying high-capacity network elements and components. Apart from the fact that this process is shortening the lifetime of network elements, the need of high capacity interfaces also increase the energy consumption (despite the effort of manufacturers in creating more efficient network element platforms). Note that nowadays there is no actual possibility of activating energy consumption proportionality (in regards the delivered traffic) to such network elements.

As a mean of slowing down this cycle of continuos renewal, and reduce the need og higher bit rate interfaces / line cards, it seems convenient to explore mechanisms that could reduce the volume of traffic without impacting the user service expectations. Variants of multicast or different service delivery strategies can help to improve the energy efficiency associated to the video streaming service. It should be noted that another front for optimization is the one related to the deployment of cache servers in the network.

## WLAN Network Energy Saving

In a WLAN network, The AP is usually powered by a PoE switch.
AP nodes are network devices with the largest number and consuming most of energy. Therefore, the working status of the AP is the core of the energy saving solution.

The working status of the AP can be break down into 3 modes as follows:
   PoE power-off mode: In this mode, the PoE switch shuts down the port and stops supplying power to the AP. The AP does not consume power at all. When the AP wakes up, the port provides power again. In this mode, it usually takes a few minutes for the AP to recover.
   Hibernation mode: Only low power consumption is used to protect key hardware such as the CPU, and other components are shut down.
   Low power consumption mode: Compared with the hibernation mode, the low power consumption mode maintains a certain communication capability. For example, the AP retains only the 2.4 GHz band and disables other radio bands.

In energy saving deployment, after the surrounding energy saving APs are shut down, the Working AP automatically adjusts their transmit power to increase the coverage of the entire area at specific energy saving period. In such case, energy saving APs can freely choose to switch to any mode we described above.


~~~~

   /---\
  |     +-----+
  | AP  |     |
   \---/      |      +------------+
              |      |            |
              |------+     PoE    |
   /---\      |      |   Switch   |
  |     |     |      +------------+
  | AP  +-----+
   \---/

~~~~
{: #poe-power-off title="PoE Power Off Mode"}

~~~~

                 4                         4
 +----------+   \|/        +----------+   \|/
 |          |    |         |          |    |
 |   +----+ |    |         |   +----+ |    |
 |   |5GHz+-+----+         |   |5GHz+-+-X--+
 |   | RF | |    2         |   | RF | |    2
 |   +----+ |   \|/    \   |   +----+ |   \|/
 |   +----+ |    |   ---\  |   +----+ |    |
 |  2.4GHz| |    |       \ |  2.4GHz| |    |
 |   | RF +-+----+       / |   | RF +-+-X--+
 |   +----+ |    2   ---/  |   +----+ |    2
 |   +----+ |   \|/    /   |   +----+ |   \|/
 |  2.4GHz| |    |         |  2.4GHz| |    |
 |   | RF |-+----+         |   | RF +-+----+
 |   +----+ |              |   +----+ |
 +----------+              +----------+

~~~~
{: #low-power-consumption title="Low Power Consumption Mode"}

~~~~

     +--+  +--+    +--+
     |AP|--|AP|--- |AP|      ------------------------------
     +--+  +--+   \+--+      Grouping  Recommended
     /               \        Area     Energy Saving Period
  +--+     +--+      +--+    ------------------------------
  |AP|     |AP|      |AP|    XED01-1  01:00:00,06:30:00
  +--+     +--+      +--+
    |                 |      ------------------------------
     +--+          +--+
     |AP|  +--+   /|AP|      XED01-2  01:30:00,06:30:00
     +--+--|AP|--- +--+     --------------------------------
           +--+

~~~~
{: #wireless-resource-management title="Wireless Resource Management on APs"}

For this use case, the following requirements apply:

|id|category|requirements|note|Pri|
|:----|:----|:----|:----|:----|
|Req01-UCWES|Control& Mgmt|Ability to switch on or off to power the L2 network device at specific time period|Network Level Mgmt|1|
|Req02-UCWES|Control& Mgmt|Ability to reconfigure various different energy saving mode to adapt to network change|Network Level Mgmt|1|
|Req03-UCWES|Control& Mgmt|Ability to optimize wireless resource management to support dynamic energy saving|Network Level Mgmt|1|
|Req04-UCWES|Control& Mgmt|Ability to schedule wireless resource management to support dynamic energy saving|Network Level Mgmt|1|

## Fixed Network Energy Saving

Traffic on the Tidal network has an obvious tidal period, including heavy-traffic periods and light-traffic periods: The time duration of heavy traffic load and light traffic load are clearly distinguished.
The switching time between the heavy-traffic period and the light-traffic period is quite fixed and cyclic.
In a tidal network, some network devices can be shut down or sleep during low-traffic periods to save energy.
In the metro or backbone network, the routers support various different speed interfaces, e.g., the gigabit level to 10GE/50GE, or 100G to 400G. Routers might choose to adjust speed of the interface or downgrade from high speed interface to low speed interface based on network traffic load changes to save the energy.
In addition, the routers can adjust the number of working network processor cores and clock frequency of chipsets and the number of SerDes buses based on network traffic load changes to save the energy.
For this use case, the following requirements apply:

|id|category|requirements|note|Pri|
|:----|:----|:----|:----|:----|
|Req01-UCFES|Control& Mgmt|Ability to shutdown devices during low traffic period|Network Level Mgmt|1|
|Req02-UCFES|Control& Mgmt|Ability to restart devices during high traffic period|Network Level Mgmt|1|
|Req03-UCFES|Control& Mgmt|Ability to adjust interface speed to adapt to network traffic change|Network Level Mgmt|1|
|Req04-UCFES|Control& Mgmt|Ability to adjust working component such as SerDes to adapt to network traffic change|Network Level Mgmt|1|

## Energy Efficiency Network Management

Network level Energy Efficiency allows network operators not only see real time energy consumption in the network devices of large scale network, but also
allow you see
o which network devices enable energy saving, which devices not,which are legacy ones,
o The total energy consumption changing trend over the time of the day, for all network devices,
o Energy efficiency changing trend over the time of the day for the whole network.
With the better observability to energy consumption statistics data and energy efficiency statistics data, the network operators can know which part of the network need to be adjusted or optimized based on network status change.
For this use case, the following requirements apply:

|id|category|requirements|note|Pri|
|:----|:----|:----|:----|:----|
|Req01-UCEEM|Discovery|Ability to provide observability to Network wide Energy Efficiency Statistics Data|Network Level Mgmt|1|
|Req02-UCEEM|Observability|Ability to provide observability to Network Wide Energy Consumption Statistics data|Network Level Mgmt|1|
|Req03-UCEEM|Observability|Ability to discover energy saving capability for each device type|Network Level Mgmt|1|

# Requirements Extracted from Proponents Documents

This section extracts and groups requirements from the documents of the GREEN WG proponents [GREEN-BOF], [sustainability-insights], [legacy-path] and [rfc6988bis-green]. The aim is to determine initial sets of requirements actionable at different levels of the framework presented below {{framework}}.

The table below groups the operator'requirements based on the inputs received from operators for the GREEN BoF [charter-refinement],[operators-inputs].

|id|category|requirements|note|Pri|
|:----|:----|:----|:----|:----|
|Req01-OP|Observability|Component granularity, e.g., per line-card, per-port|Per component measure|1|
|Req02-OP|Observability|Availability of information on the power consumption of the device, without needing instrument connected to the infra|Related to connected device case|1|
|Req03-OP|Observability|Triggering of alarms when consumption deviate from a nominal usage|Alarm notification|1|
|Req04-OP|Observability|Improvement of metering solutions (finer granularity, control of the energy efficiency and saving, interoperability, exposure)|Standardized metering|1|
|Req05-OP|Analysis|Common definition of energy efficiency in network devices/components|Standard metric|1|
|Req06-OP|Analysis|Common methodology of measurements for fair comparison|Standard methodology|2|
|Req07-OP|Analysis|How to provide accurate figures (context of the measurement in terms of time period, location, traffic, etc|Time based, location based visualn|2|
|Req08-OP|Analysis|Database for decision in case of large data transfer|Information Correlation|3|
|Req09-OP|Analysis|Ability of multi-layer analysis (e.g., IP plus optical)|POI Use Case|3|
|Req10-OP|Control& Mgmt|To have devices with elastic power consumption according to the carried traffic|Dynamic Energy Saving|2|
|Req11-OP|Control& Mgmt|Support of network-wide energy saving and optimization functions|Network Level Mgmt|2|
|Req12-OP|Control& Mgmt|Support of network-wide control of energy optimization APIs, allowing external applications to optimize consumption|Network Level Mgmt|2|
|Req13-OP|Control& Mgmt|Advanced sleep mode, needing some sort of low power mode when node is lightly utilized|Dynamic Energy Saving|2|
|Req14-OP|Control& Mgmt|Ability to steer traffic based on power savings|Traffic Engineering|4|
|Req15-OP|Control& Mgmt|Comparison of decision vs optimal case|Intent based Concept|2|
|Req16-OP|Control& Mgmt|Synchronous query support|Network Level Query|2|
|Req17-OP|Inventory Management|Inventory of power components (of devices, racks, etc) including together|Component & Device Level|1|
|Req18-OP|Interaction with other domain|Inclusion of data center networks in the picture|Data Center Case|3|
|Req19-OP|Interaction with other domain|Inclusion of data center networks in the picture|Mobile Network Case|3|
|Req20-OP|Sustainability & Carbon Emission|Optimize the overall CO2 footprint (i.e., energy mix based on source type) facilitating the engineering of PoP More renewable energy|More renewable energy|4|
|Req21-OP|Sustainability & Carbon Emission|Support GHG units|Measurement Units|4|
|Req22-OP|Sustainability & Carbon Emission|Support Energy units|More renewable energy|2|
|Req23-OP|Sustainability & Carbon Emission|Accounting of legacy installed based GHG/energy|Accounting Cost|4|
|Req24-OP|Sustainability & Carbon Emission|Track device/network Energy Consumption Before Operation|Manufacturing, transport (weight, volume, package)|4|

The table below groups requirements from [rf988bis-green] draft Open Issues.

TODO: this table has to be reviewed as it part of it overlaps with the sections above related to rfc6988

|id|category|requirements|note|Pri|
|:----|:----|:----|:----|:----|
|Req01-BIS|Control& Mgmt|Distinguish backup from main power sources|rfc6988bis battery(i)| 2|
|Req02-BIS|Inventory Management|Reporting on Other Entities, typically smart PDU or PoE|Fit in "Inventory of power components (of devices, racks, etc) including together"| 2|
|Req03-BIS|Observability or Interaction with Other domain|Room sensor (hvac...)|Data Center Case| 4|
|Req04-BIS|Observability|flexible (future-proof) description of the nature of the sources of the energy used |Standard metric|2 |

(i) It is crucial to know when a device is powered by a backup source for many obvious reasons

The table below groups requirements from [sustainability-insights] uses cases related to energy consumption vs sustainability

|id|category|requirements|note|Pri|
|:----|:----|:----|:----|:----|
|Req01-SIS|Observability|Provide near-real-time energy consumption to different device types, service types, and individual users | Helps identify which devices or network functions are consuming more energy. | 2 |
|Req02-SIS|Migration or Upgrade | Provide KPIs for energy efficiency parameters, enhance accuracy of upgrade decisions | Helps make informed decisions about upgrades based on actual usage data. |   |
|Req03-SIS|Recycling | Report on percentage of recycled user devices and components. Enable comprehensive reporting and recycling efforts | Major driver of the circular economy, transparency is key | 4 |
|Req04-SIS|Power Optimization | Provide KPIs for energy efficiency parameters. Perform actions to reduce energy consumption | Monitor network and application performance to optimize power usage | 4 |
|Req05-SIS|Control& Mgmt Switch off | Stop and restart WiFi APs with the right time, space, and service granularity | Save power consumption during periods when APs are not in use.| 2|

# EMAN Requirements from RFC6988bis

TODO: This section will groups the subsections requirements in tables to prepare the room for establishing their individual consensus priority.

This section groups the inputs of the work of RFC6988bis [rfc6988bis-green]. Currently they still include a lot of verbatim text from [rfc6988] which don't fit exactly in the granularity of the current GREEN WG charter.

Specifications made by the IETF, aka in WGs like EMAN, on energy managements focus mainly on SMI (aka MIBs) instead of YANG and cover neither the control nor energy efficiency. By consequence all EMAN WG requirements might not be applicable to the GREEN WG charter as they can worded and arraged differently. As an example battery is in the scope as a source of power but the detail of the management of the battery is not a requirement.

The goal is to enable the resuse pieces of the energy-related requirements of RFC6988 and to map them in a framework of YANG/Netconf for energy efficiency that might reuse "YANG Data Model for Hardware Management" {{?RFC8348}}, a conversion of former Entity MIB module, Entity Sensor MIB module, Entity State MIB modules.

   Section 4.2 elaborates on a set of general needs for Energy Management.
   Requirements for an Energy Management standard are specified in
   Sections 4.3 through 4.6.

   Sections 4.4 through 4.5 contain conventional requirements specifying
   information on entities and control functions.

   Sections 4.6 contains requirements specific to Energy Management.
   Due to the nature of power supply, some monitoring and control
   functions are not conducted by interacting with the entity of
   interest but rather with other entities, for example, entities
   upstream in a power distribution tree.

## Conventional Requirements for Energy Efficiency Management

   The specification of requirements for an Energy Efficiency Management standard
   starts with Section 4.3, which addresses the identification of entities
   and the granularity of reporting of energy-related information.  A
   standard must support the unique identification of entities,
   reporting per network, per entire device, and reporting energy-related information
   on individual components of a device or attached devices.

   Section 4.4 specifies requirements related to the monitoring of
   entities.  This includes general (type, context) information and
   specific information on Power States, Power Inlets, Power Outlets,
   power, energy.  The control of Power State and power saving functionalities,
  optimization functionalities by entities is covered by requirements specified in Section 5.6.

## General Considerations Related to Energy Management

   The basic objective of Energy Efficiency Management is to operate sets of
   network devices using minimal energy, while maintaining a certain level of
   service.

### Power States

   Entities can be set to an operational state that results in the
   lowest power level that still meets the service-level performance
   objectives.  In principle, there are three basic types of Power
   States for an entity or for a whole system:

   o  full Power State

   o  sleep state (not functional but immediately available)

   o  off state (may require significant time to become operational)

   In specific network devices, the number of Power States and their properties
   vary considerably.  Simple entities may only have the extreme states:
   full Power State and off state.  Many network devices have three basic Power
   States: on, off, and sleep.  However, more finely grained Power
   States can be implemented, especially when Energy efficiency gains for communication
   systems are highly sought after, for environmental, business, and technical reasons.
   Examples are various operational low Power States in which a network device requires less energy than in the full
   power "on" state, but -- compared to the sleep state -- is still
   operational with reduced performance or functionality.

   Another example is standby power state
   in which network device has multiple standby components and one active component for the same functionality,
   standby components are partially functional and can be immediately available when active component is down.
   The standby power state can be introduced to save energy while impove the overall network utilization.

### Saving Energy versus Maintaining Service Level

   One of the objectives of Energy Efficiency Management is to reduce energy
   consumption.  While this objective is clear, attaining that goal is
   often difficult.  In many cases, there is no way to reduce power
   without the consequence of a potential service (performance or
   capacity) degradation.  In this case, a trade-off needs to be made
   between service-level objectives (e.g., network performance) and
   energy minimization. In other cases, a reduction of power can easily be achieved
   while still maintaining sufficient service-level performance, for example, by
   switching entities to lower Power States when higher performance is
   not needed. To measure of the trade-off between service-level object and energy
   consumption, a new set of energy efficiency metrics needs to defined.

### Local versus Network-Wide Energy Management

   Many energy-saving functions are executed locally by an entity; it
   monitors its usage and dynamically adapts its power according to the
   required performance.  It may, for example, switch to a sleep state
   or backup state when it is not in use, or outside of scheduled business hours. An
   Energy Efficiency Management System may observe an entity's Power State and
   configure or optimize its power-saving policies.

   Energy savings can also be achieved with policies implemented by a
   network management system that controls Power States of managed
   entities.  Information about the power received and provided by
   entities in different Power States may be required in order to set
   such policies.  Often, this information is best acquired through
   monitoring.

   Network-wide and local Energy Management methods both have advantages
   and disadvantages, and it is often desirable to combine them.
   Central management is often favorable for setting Power States of a
   large number of entities at the same time, for example, at the
   beginning and end of business hours in a building.  Local management
   is often preferable for power-saving measures based on local
   observations, such as the high or low functional load of an entity.

### Energy Monitoring versus Energy Saving

   Monitoring energy, power, and Power States alone does not reduce the
   energy needed to run an entity.  In fact, it may even increase it
   slightly due to monitoring instrumentation that needs energy.
   Reporting measured quantities over the network may also increase
   energy use, though the acquired information may be an essential input
   to control loops that save energy.

   Monitoring energy and Power States can also be required for other
   purposes, including:

   o  investigating energy-saving potential

   o  evaluating the effectiveness of energy-saving policies and
      measures

   o  deriving, implementing, and testing power management strategies

   o  accounting for the total power received and provided by an entity,
      a network, or a service

   o  predicting an entity's reliability based on power usage

   o  choosing the time of the next maintenance cycle for an entity



### Overview of Energy Management Requirements

   The following basic management functions are required:

   o  monitoring Power States

   o  monitoring power (energy conversion rate)

   o  monitoring (accumulated) received and provided energy

   o  monitoring Power Attributes

   o  setting Power States

   In addition, to support energy efficiency management, additional requirements concerned with discovery functions
   and control functions are introduced:

   o   discovering energy-managed network, devices and their components

   o   discovering inventory of power components together with their capabilities, optimization
        control capabilities, nominal condition use

   o  discovering supported power state of each network device within the network

   o discovering power relationship between component within network device and across network devices.

   o  support additional energy efficiency metrics for energy efficiency monitoring, e.g., heat consumption, energy
       efficiency ratio, maximum wake up time, etc.

   o  support separation of desired power state and actual power state and optimize energy usage to allow update actual
       power state to match desired power state.

  o  Introduce energy saving method, and energy efficiency metrics to support explicit power control or energy
      efficiency optimization and control.

  o  allow control and optimize energy usage to make the trade-off between network performance and power
     consumption.

  o support both local management and network wide management based on energy saving
     functionality.

   Energy usage control and optimization is complementary to other energy-saving design, such
   as low-power electronics,  energy-efficient device design (for example, low-power modes for components), and
   energy-efficient network architectures and is exercised using management interface.  Measurement of received and
   provided energy can provide useful data for energy efficiency management.

## Identification of Entities

   Entities must be capable of being uniquely identified within the
   context of the management system.  This includes entities that are
   components of managed devices as well as entire devices or the entire network.

   Entities that report on or control other entities must identify the
   entities they report on or control: see Section 7 or Section 8,
   respectively, for the detailed requirements.

   An entity may be an entire network, or network device or a component of it.  Examples of
   components of interest are a hard drive, a fan, or a line card.
   The ability to control individual components to save energy may be
   required.  For example, server blades can be switched off when the
   overall load is low, or line cards at switches may be powered down at
   night.

   Identifiers for network, network devices and components are already defined in
   standard YANG modules Network Topology YANG module {{?RFC8345}} and Hardware YANG
   module {{?RFC8348}}. Note that Network Topology YANG module {{?RFC8345}} identifiers
   are reused in the Network Inventory YANG module  {{?I-D.ietf-ivy-network-inventory-yang}}
   and are also the basis for the Digital Map Modeling efforts in the NMOP Working Group.

   Instrumentation for measuring the received and provided energy of a
   device is typically more expensive than instrumentation for
   retrieving its Power State.  Many devices may provide Power State
   information for all individual components separately, while reporting
   the received and provided energy only for the entire device.

### Identifying Entities

   The standard must provide means for uniquely identifying entities.
   Uniqueness must be preserved such that collisions of identities are
   avoided at potential receivers of monitored information.

### Identifying Entitiy Capabilities

   The standard must provide means for discovering inventory of power components
   together with their capabilities, optimization control capabilities, nominal
   condition use. In addition, The standard must provide means for discovering
   supported power state of each network device within the network and power
   relationship between component within network device and across network devices.

### Persistence of Identifiers

   The standard must provide means for indicating whether identifiers of
   entities are persistent across a restart of the entity.

### Change of Identifiers

   The standard must provide means to indicate any change of entity
   identifiers.

### Using Entity Identifiers of Existing YANG Modules

   The standard must provide means for reusing entity identifiers from
   existing standards, including at least the following:

   o  the network-id, link-id, node-id, port-id of the Network Topology YANG module {{?RFC8345}}

   o  the ne-id, Universal Unique IDentifier (UUID) of the network element and component-id, UUID of each component within the network element in Network Inventory YANG module {{?I-D.ietf-ivy-network-inventory-yang}}

   o  the name, UUID of each hardware component in the Hardware YANG module {{?RFC8348}}


   Generic means for reusing other entity identifiers must be provided.

## Information on Entities

   This section describes information on entities for which the standard
   must provide means for retrieving and reporting.

   Required information can be structured into seven groups.
   Section 5.1 specifies requirements for general information on
   entities, such as type of entity or context information.
   Requirements for information on Power Inlets and Power Outlets of
   entities are specified in Section 5.2.  The monitoring of power and
   energy is covered by Sections 5.3 and 5.5, respectively.  Section 5.4
   covers requirements related to entities' Power States.  Finally, the
   reporting of time series of values is covered by Section 5.7.

### General Information on Entities

   For Energy Management, understanding the role and context of an
   entity may be required.  An Energy Management System may aggregate
   values of received and provided energy according to a defined
   grouping of entities.  When controlling and setting Power States, it
   may be helpful to understand the grouping of the entity and role of
   an entity in a network.  For example, it may be important to exclude
   some mission-critical network devices from being switched to lower
   power or even from being switched off.

#### Type of Entity

   The standard must provide means to configure, retrieve, and report a
   textual name or a description of an entity.

#### Context of an Entity

   The standard must provide means for retrieving and reporting context
   information on entities, for example, tags associated with an entity
   that indicate the entity's role.

#### Significance of Entities

   The standard must provide means for retrieving and reporting the
   significance of entities within its context, for example, how
   important the entity is.

#### Power Priority

   The standard must provide means for retrieving and reporting power
   priorities of entities.  Power priorities indicate an order in which
   Power States of entities are changed, for example, to lower Power
   States for saving power.

#### Grouping of Entities

   The standard must provide means for grouping entities.  This can be
   achieved in multiple ways, for example, by providing means to tag
   entities, assign them to domains, or assign device types to them.

### Power Interfaces

   A Power Interface is an interface at which a device is connected to a
   power transmission medium, at which it can in turn receive power,
   provide power, or both.

   A Power Interface is either an inlet or an outlet.  Some Power
   Interfaces change over time from being an inlet to being an outlet
   and vice versa.  However, most Power Interfaces never change.

   Network Devices have Power Inlets at which they are supplied with electric
   power.  Most devices have a single Power Inlet, while some have
   multiple inlets.  Different Power Inlets on a device are often
   connected to separate power distribution trees.  For Energy
   Monitoring, it is useful to retrieve information on the number of
   inlets of a device, the availability of power at inlets, and which
   inlets are actually in use.

   Network Devices can have one or more Power Outlets for supplying other
   devices with electric power.

   For identifying and potentially controlling the source of power
   received at an inlet, identifying the Power Outlet of another network device
   at which the received power is provided may be required.
   Analogously, for each outlet, it is of interest to identify the Power
   Inlets that receive the power provided at a certain outlet.  Such
   information is also required for constructing the wiring topology of
   electrical power distribution to devices.

   Static properties of each Power Interface are required information
   for Energy Efficiency Management.  Static properties include the kind of
   electric current (AC or DC), the nominal voltage, the nominal AC
   frequency, and the number of AC phases.  Note that the nominal
   voltage is often not a single value but a voltage range, such as, for
   example, (100V-120V), (100V-240V), (100V-120V,220V-240V).

#### List of Power Interfaces

   The standard must provide means for monitoring the list of Power Interfaces of a device.

#### Operational Mode of Power Interfaces

   The standard must provide means for monitoring the operational mode of a Power Interface, which is either "Power Inlet" or "Power Outlet".

#### Corresponding Power Outlet

   The standard must provide means for identifying the Power Outlet that
   provides the power received at a Power Inlet.

#### Corresponding Power Inlets

   The standard must provide means for identifying the list of Power
   Inlets that receive the power provided at a Power Outlet.

#### Availability of Power

   If the Power States allow it, the standard must provide means for
   monitoring the availability of power at each Power Interface.  This
   includes indicating whether a power supply at a Power Interface is
   switched on or off.

#### Use of Power

   The standard must provide means for monitoring each Power Interface
   if it is actually in use.  For inlets, this means that the device
   actually receives power at the inlet.  For outlets, this means that
   power is actually provided from the outlet to one or more devices.

#### Type of Current

   The standard must provide means for reporting the type of current (AC
   or DC) for each Power Interface as well as for a device.

#### Nominal Voltage Range

   The standard must provide means for reporting the nominal voltage
   range for each Power Interface.

#### Nominal AC Frequency

   The standard must provide means for reporting the nominal AC
   frequency for each Power Interface.

#### Number of AC Phases

   The standard must provide means for reporting the number of AC phases
   for each Power Interface.

### Power

   Power is measured as an instantaneous value or as the average over a
   time interval.

   Obtaining highly accurate values for power and energy may be costly
   if dedicated metering hardware is required.  Entities without the
   ability to measure with high accuracy their power, received energy,
   and provided energy may just report estimated values, for example,
   based on load monitoring, Power State, or even just the entity type.

   Depending on how power and energy values are obtained, the confidence
   in a reported value and its accuracy will vary.  Entities reporting
   such values should qualify the confidence in the reported values and
   quantify the accuracy of measurements.  For reporting accuracy, the
   accuracy classes specified in IEC 62053-21 [IEC.62053-21] and
   IEC 62053-22 [IEC.62053-22] should be considered.

   Further properties of the power supplied to a device are also of
   interest.  For AC power supply in particular, several Power
   Attributes beyond the real power are of potential interest to Energy
   Management Systems.  The set of these properties includes the complex
   Power Attributes (apparent power, reactive power, and phase angle of
   the current or power factor) as well as the actual voltage, the
   actual AC frequency, the Total Harmonic Distortion (THD) of voltage
   and current, and the impedance of an AC phase or of the DC supply.  A
   new standard for monitoring these Power Attributes should be in line
   with already-existing standards, such as [IEC.61850-7-4].

   For some network management tasks, it is desirable to receive
   notifications from entities when their power value exceeds or falls
   below given thresholds.

#### Real Power / Power Factor

   The standard must provide means for reporting the real power for each
   Power Interface as well as for an entity.  Reporting power includes
   reporting the direction of power flow.

#### Power Measurement Interval

   The standard must provide means for reporting the corresponding time
   or time interval for which a power value is reported.  The power
   value can be measured at the corresponding time or averaged over the
   corresponding time interval.

#### Power Measurement Method

   The standard must provide means to indicate the method used to obtain
   these values.  Based on how the measurement was conducted, it is
   possible to associate a certain degree of confidence with the
   reported power value.  For example, there are methods of measurement
   such as direct power measurement, estimation based on performance
   values, or hard-coding average power values for an entity.

#### Accuracy of Power and Energy Values

   The standard must provide means for reporting the accuracy of
   reported power and energy values.

#### Actual Voltage and Current

   The standard must provide means for reporting the actual voltage and
   actual current for each Power Interface as well as for a device.  For
   AC power supply, means must be provided for reporting the actual
   voltage and actual current per phase.

#### High-Power/Low-Power Notifications

   The standard must provide means for creating notifications if power
   values of an entity rise above or fall below given thresholds.

#### Complex Power / Power Factor

   The standard must provide means for reporting the complex power for
   each Power Interface and for each phase at a Power Interface.  In
   addition to the real power, at least two of the following three
   quantities need to be reported: apparent power, reactive power, and
   phase angle.  The phase angle can be substituted by the power factor.

#### Actual AC Frequency

   The standard must provide means for reporting the actual AC frequency
   for each Power Interface.

#### Total Harmonic Distortion

   The standard must provide means for reporting the Total Harmonic
   Distortion (THD) of voltage and current for each Power Interface.
   For AC power supply, means must be provided for reporting the THD per
   phase.

#### Power Supply Impedance

   The standard must provide means for reporting the impedance of a
   power supply for each Power Interface.  For AC power supply, means
   must be provided for reporting the impedance per phase.

### Power State

   Many entities have a limited number of discrete Power States.

   There is a need to report the actual Power State of an entity and to
   provide the means for retrieving the list of all supported Power
   States.

   Different standards bodies have already defined sets of Power States
   for some entities, and others are creating new Power State sets.  In
   this context, it is desirable that the standard support many of these
   Power State standards.  In order to support multiple management
   systems that possibly use different Power State sets while
   simultaneously interfacing with a particular entity, the Energy
   Management System must provide means for supporting multiple Power
   State sets used simultaneously at an entity.

   Power States have parameters that describe their properties.  It is
   required to have a standardized means for reporting some key
   properties, such as the typical power of an entity in a certain
   state.

   There is also a need to report statistics on Power States, including
   the time spent as well as the received and provided energy in a Power
   State.

#### Actual Power State

   The standard must provide means for reporting the actual Power State
   of an entity.

#### List of Supported Power States

   The standard must provide means for retrieving the list of all
   potential Power States of an entity.

#### Multiple Power State Sets

   The standard must provide means for supporting multiple Power State
   sets simultaneously at an entity.

#### List of Supported Power State Sets

   The standard must provide means for retrieving the list of all Power
   State sets supported by an entity.

#### List of Supported Power States within a Set

   The standard must provide means for retrieving the list of all
   potential Power States of an entity for each supported Power State
   set.

#### Typical Power Per Power State

   The standard must provide means for retrieving the typical power for
   each supported Power State.

#### Power State Statistics

   The standard must provide means for monitoring statistics per Power
   State, including the total time spent in a Power State, the number of
   times each state was entered, and the last time each state was
   entered.  More Power State statistics are addressed by the
   requirements in Section 5.5.3.

#### Power State Changes

   The standard must provide means for generating a notification when
   the actual Power State of an entity changes.

### Energy

   The monitoring of electrical energy received or provided by an entity
   is a core function of Energy Management. Since energy is an
   accumulated quantity, it is always reported for a certain interval of
   time.  This can be, for example, the time from the last restart of
   the entity to the reporting time, the time from another past event to
   the reporting time, the last given amount of time before the
   reporting time, or a certain interval specified by two timestamps in
   the past.

   It is useful for entities to record their received and provided
   energy per Power State and report these quantities.

  In addition, it is also useful for entities to record energy attributes
  such as maximum wake up time, maximum sleep time, service interruption
  time, transition time, maximum packet throughput, maximum bit throughput
  and report these quantities.

#### Energy Measurement

   The standard must provide means for reporting measured values of
   energy and the direction of the energy flow received or provided by
   an entity.  The standard must also provide the means to report the
   energy passing through each Power Interface.

#### Energy Efficiency Measurement

  The standard must provide means for measuring the trade-off between
  service-level object and energy consumption. [ETSI-ES-203-136],
  [ITUT-L.1310], [ATIS-0600015.03.2013] provide methodology and test
  procedure for measuring such energy efficiency related metrics, which
  is defined as the throughput forwarded by 1 watt. The traffic loads and
  the weighted multipliers need to be clearly established in advance.

  Note that, based on the specific optimization policy (throughput, heat,
  energy source, etc.), different derived metrics should be computed at
  the controller level.

#### Power Gain Measurement

  The standard must provide means for measuring power gain, which can
  be calculated by actual power to be consumed by the entity divided by the maximum
  power of the entity. In addition, the minimum power gain can also be
  measured and reported.

#### Time Intervals

   The standard must provide means for reporting the time interval for
   which an energy value is reported.

#### Energy Per Power State

   The standard must provide means for reporting the received and
   provided energy for each individual Power State.  This extends the
   requirements on Power State statistics described in Section 5.4.7.

### Time Series of Measured Values

   For some network management tasks, obtaining time series of measured
   values from entities, such as power, energy, etc., is
   required.

   In general, time series measurements could be obtained in many
   different ways.  Means should be provided to either push such values
   from the location where they are available to the management system
   or to have them stored locally for a sufficiently long period of time
   such that a management system can retrieve the full time series.

   The following issues are to be considered when designing time series
   measurement and reporting functions:

   1.  Which quantities should be reported?

   2.  Which time interval type should be used (total, delta, sliding
       window)?

   3.  Which measurement method should be used (sampled, continuous)?

   4.  Which reporting model should be used (push or pull)?

   The most discussed and probably most needed quantity is energy.  But
   a need for others, such as power, can be identified as well.

   There are three time interval types under discussion for accumulated
   quantities such as energy.  They can be reported as total values,
   accumulated between the last restart of the measurement and a certain
   timestamp.  Alternatively, energy can be reported as delta values
   between two consecutive timestamps.  Another alternative is reporting
   values for sliding windows as specified in [IEC.61850-7-4].

   For non-accumulative quantities, such as power, different measurement
   methods are considered.  Such quantities can be reported using values
   sampled at certain timestamps or, alternatively, by mean values for
   these quantities averaged between two (consecutive) timestamps or
   over a sliding window.

   Finally, time series can be reported using different reporting
   models, particularly push-based or pull-based.  Push-based reporting
   can, for example, be realized by reporting power or energy values
   using the NETCONF protocol {{?RFC6241}}.  The NETCONF a protocol can
   also be used to realize pull-based reporting of time series.

   For reporting time series of measured values, the following
   requirements have been identified.  Further decisions concerning
   issues discussed above need to be made when developing concrete
   Energy Management standards.

#### Time Series of Energy Values

   The standard must provide means for reporting time series of energy
   values.  If the comparison of time series between multiple entities
   is required, then time synchronization between those entities must be
   provided (for example, with the Network Time Protocol {{?RFC5905}}).

#### Time Series Interval Types

   The standard must provide means for supporting alternative interval
   types.  The requirement in Section 5.5.2 applies to every reported
   time value.

#### Time Series Storage Capacity

   The standard should provide means for reporting the number of values
   of a time series that can be stored for later reporting.

## Control of Entities

   Many entities control their Power State locally.  Other entities need
   interfaces for an Energy Management System to control their Power
   State.

   A power supply is typically not self-managed by devices, and control
   of a power supply is typically not conducted as an interaction
   between an Energy Management System and the device itself.  It is
   rather an interaction between the management system and a device
   providing power at its Power Outlets.  Similar to Power State
   control, power supply control may be policy driven.  Note that
   shutting down the power supply abruptly may have severe consequences
   for the device.

### Provisioning Power States

   The standard must provide means for provisioning Power States of entities.

   When an Energy Object is set to a particular Power State, the
   represented device or component may be busy.  The Energy Object
   should set the desired Power State and then update the actual Power
   State when the device or component changes. The standard must
   provide means to report the intented and applied Power States,
   with the Network Management Datastore Architecture (NMDA) {{?RFC8342}}

### Controlling Power SupplyProvisioning

   The standard must provide means for switching a power supply off or
   turning a power supply on at Power Interfaces providing power to one
   or more devices.

### Controlling Switching Power Speed

   The standard must provide means to avoid the speed of switching a power supply off or turning a power supply on to break component parts (aka laser, power parts, wire connectors ...),  or a too hight number of on/off switching to reduce their live duration.

### Controlling Energy Saving and Optimization Functionalities

  The standard must provide means for controlling energy saving and
  optimization functionalities and allocating the committed component resource
  (e.g., adjust fan speed, shutdown high speed interface) or committed device
  resource (e.g., multiple cards scheduling, multiple power module scheduling).

  In addition, the standard must provide means to support both local management and
  network wide management based on energy saving functionality.

## Management of oultet Entities

As discussed in Section 5, not all energy-related information may be
   available at the entity in question.  Such information may be
   provided by other entities.  This section groups the requirements for the discovery, the reporting and the control
   of information.

The intend is to summarize them in a table in section 9.

### Discovery of Power inlet Entities

Energy consumption must not be accounted twice

#### Reporting on Other Entities

   As discussed in Section 5, not all energy-related information may be
   available at the entity in question.  Such information may be
   provided by other entities.  This section covers only the reporting
   of information.  See Section 8 for requirements on controlling other
   entities.

   There are cases where a power supply unit switches power for several
   entities by turning power on or off at a single Power Outlet or where
   a power meter measures the accumulated power of several entities at a
   single power line.  Consequently, it should be possible to report
   that a monitored value does not relate to just a single entity but is
   an accumulated value for a set of entities.  All of the entities
   belonging to that set need to be identified.

#### Reports on Other Entities

   The standard must provide means for an entity to report information
   on another entity.

#### Identity of Other Entities on Which Information Is Reported

   For entities that report on one or more other entities, the standard
   must provide means for reporting the identity of other entities on
   which information is reported.  Note that, in some situations, a
   manual configuration might be required to populate this information.

#### Reporting Quantities Accumulated over Multiple Entities

   The standard must provide means for reporting the list of all
   entities from which contributions are included in an accumulated
   value.

#### List of All Entities on Which Information Is Reported

   For entities that report on one or more other entities, the standard
   must provide means for reporting the complete list of all those
   entities on which energy-related information can be reported.

#### Content of Reports on Other Entities

   For entities that report on one or more other entities, the standard
   must provide means for indicating what type or types of energy-
   related information can be reported, and for which entities.

### Controlling Other Entities

   This section specifies requirements for controlling Power States and
   power supply of entities by communicating with other entities that
   have the means for doing that control.

#### Controlling Power States of Other Entities

   RFC6988 allow some entities have control over Power States of other entities,
   e.g., in Building automation case where a gateway to a building system may have
   the means to control the Power State of entities in the building that do not have
   an IP interface.

   In this document, we assume all network devices have IP connectivity in the operator
   controlled environment. Therefore only an Energy Management System has control over
   Power States of other entities.

   In addition, it is required that an entity that has its state
   controlled by the Energy Management System has the means to report the list of
   these other entities.

##### Control of Power States of Other Entities

   The standard must provide means for an Energy Management System to
   send Power State control commands to an entity that controls the
   Power States of entities other than the entity to which the command
   was sent.

##### Identity of Other Power State Controlled Entities

   The standard must provide means for reporting the identities of the
   entities for which the reporting entity has the means to control
   their Power States.  Note that, in some situations, a manual
   configuration might be required to populate this information.

##### List of All Power State Controlled Entities

   The standard must provide means for an entity to report the list of
   all entities for which it can control the Power State.

##### List of All Power State Controllers

   The standard must provide means for an entity that receives commands
   controlling its Power State from other entities to report the list of
   all those entities.

#### Controlling Power Supply

   Some entities may have control of the power supply of other entities,
   for example, because the other entity is supplied via a Power Outlet
   of the entity.  For this and similar cases, means are needed to make
   this control accessible to the Energy Management System.  This need
   is already addressed by the requirement in Section 6.2.

   In addition, it is required that an entity that has its supply
   controlled by other entities has the means to report the list of
   these other entities.  This need is already addressed by requirements
   in Sections 5.2.3 and 5.2.4.

# Framework Discussed During the BoF {#framework}

The overall framework is shown in {{green-framework}}.

~~~~

       What needs to be standardized for Framework


(3) Network Domain Level :

(a)              (b)              (c)
Inventory        Monitor       +- DataSheets/DataBase and/or via API
Of identity      Energy        |  Metadata and other device/component
and Capability   Efficiency    |  /network related information:
     ^               ^         |
     |               |         |  .Power/Energy related metrics
     |               |         |  .information
     |               |         |  .origin of Energy Mix
     |               |         |  .carbon aware based on location
     |               |         |
     |               |         |
     |               |         |
     |               |         v
+--------------------------------------------------------------------+
|                   *                                                |
|     (2) controller   (collection, compute and aggregate?)          |
|                                                                    |
+--------------------------------------------------------------------+
             ^              ^                   ^ |
  (d)        |  (e)         |  (f)              | |(g)
  Inventory  |  Monitor     |  GREEN WG:        | |GREEN WG: Control
  Capability |  Traffic     |  Monitor power    | |(Energy saving
             |  & power     |  Proportion,      | |Functionality
             |  consumption |  Energy efficiency| |Localized mgmt/
             |              |  ratio, etc)      | |network wide mgmt)
             |              |                   | |
             |              |                   | |
             |              |                   | v
+--------------------------------------------------------------------+
|                                            *                       |
|                  (1) Device/Component Level                        |
|                                                                    |
| +---------+  +-----------+  +----------------+  +----------------+ |
| | (I)     |  | (II)      |  | (III)          |  | (IV)           | |
| | Network |  | Device    |  | Legacy Network |  | 'Attached'(PoE | |
| | Device  |  | Component |  | Device         |  | kind) Device   | |
| |         |  |           |  |                |  |                | |
| +---------+  +-----------+  +----------------+  +----------------+ |
+--------------------------------------------------------------------+

(*) Energy Efficiency Management Function is implemented inside the
device or in a controller

~~~~
{: #green-framework title="Framework discussed during the BoF"}

The main elements in the framework are as follows:

(a),(d) Discovery and Inventory

(b),(c) GREEN Metrics

(b),(f) Monitor energy efficiency

(e) Monitor power consumption and traffic (IPPM WG throughput, traffic load, etc)

(g) Control Energy Saving

# Security Considerations

   Controlling Power State and power supply of entities are considered
   highly sensitive actions, since they can significantly affect the
   operation of directly and indirectly connected devices.  Therefore,
   all control actions addressed in Sections 6 and 8 must be
   sufficiently protected through authentication, authorization, and
   integrity protection mechanisms.

   Entities that are not sufficiently secure to operate directly on the
   public Internet do exist and can be a significant cause of risk, for
   example, if the remote control functions described in Sections 6 and
   8 can be exercised on those devices from anywhere on the Internet.
   The standard needs to provide means for dealing with such cases.  One
   solution is providing means that allow the isolation of such devices,
   e.g., behind a sufficiently secured gateway.  Another solution is to
   allow compliant implementations to disable sensitive functions, or to
   not implement such functions at all.

   The monitoring of energy-related quantities of an entity as addressed
   in Sections 5 through 8 can be used to derive more information than
   just the received and provided energy; therefore, monitored data
   requires protection.  This protection includes authentication and
   authorization of entities requesting access to monitored data as well
   as confidentiality protection during transmission of monitored data.
   Privacy of stored data in an entity must be taken into account.
   Monitored data may be used as input to control, accounting, and other
   actions, so integrity of transmitted information and authentication
   of the origin may be needed.

## Secure Energy Management

   The standard must provide privacy, integrity, and authentication
   mechanisms for all actions addressed in Sections 5 through 8.  The
   security mechanisms must meet the security requirements detailed in
   Section 1.4 of {{?RFC3411}}.

## Isolation of Insufficiently Secure Entities

   The standard must provide means to allow the isolation of entities
   that are not sufficiently secure to operate on the public Internet,
   e.g., behind a gateway that implements sufficient security that the
   vulnerable entities are not directly exposed to the Internet.

## Optional Restriction of Functions

   The standard must allow compliant implementations to disable
   sensitive functions, or to not implement such functions at all, when
   operating in environments that are not sufficiently secured.  This
   applies particularly to the control functions described in Sections 6
   and 8.

## Other Aspects

Adding new interfaces on devices increase attack surfaces.
Devices have brief variation of power consumption due their internal works. Reducing the power available may reduce their routing capacity which may reduce network performance and resiliency.

# IANA Considerations

This document has no IANA actions.

# Acknowledgments

The contribution of Luis M. Contreras to this document has been supported by the Smart Networks and Services Joint Undertaking (SNS JU) under the European Union's Horizon Europe research and innovation projects 6Green (Grant Agreement no. 101096925) and Exigence (Grant Agreement no. 101139120).

# Open Issues

## Open Issues to be Discussed at IETF121

o	Consider 5g vs network slicing: 3GPP spec describong energy efficiency KPIs. 3GPP TS 28.554. Reference:https://datatracker.ietf.org/doc/rfc9543/
o	POE use case: open issue section?
o	Reduce traffic (video streaming)
o	Connectivity from radio side (trying to control the traffic/related work to CCAMP)
o	Marisol to add one use case: drift from data specifications... (somehow link to the above)
o	Use case per Domain specific? Meanwhile, they are considered as part of the network... Servers might be considered outside of scope
o	Energy Metric in E2E view

## Open Issues collected since the BoF

  o Power and Energy Monitoring and Control MIB modules has not been converted yet into YANG modules. Based on their deployements status, discuss their reuse and their mapping in Yang for energy monitoring

  o Do we need to keep a reference to the MIB object entPhysicalUUID (in section 4.4 from ENTITY-MIB v4) in case of legacy device (MIB)?

   o The EMAN requirements and EMAN framework had a lot of emphasis on the "Reporting on Other Entities", typically smart PDU or PoE.
   Is this important? Should this be removed? Should it be addressed in a future charter?
   This is text about "Sections 7 and 8 contain requirements specific to Energy Management. Due to the nature of power supply, some monitoring and control functions are not conducted by interacting with the entity of interest but rather with other entities, for example, entities upstream in a power distribution tree."

   Expressed differently: Out of scope for the short term approach of EMAN framework enhancements, but might be good to call it out, EMAN
   doesn't include mechanisms for integrating occupancy sensors or user behavior analytics, which can be critical for optimizing HVAC, lighting, and other systems for energy efficiency. This is a key aspect for Smart Buildings and Data Centers energy efficiency metrics.

   o It's not clear whether we need new Power State (Set)? Maybe not but we need to explain the mapping of existing energy efficient features to specific Power States.

   o basic (scalar) units are not enough to describe Power Data Unit capabilities and/or output. We need a more complex structure (which might already exist?)
   to cover and combine meanings (that I copied from the chats) like CO2 footprint, clean energy, mix, renewable. as an example, this should help to describe
   reduction of energy consumption and the increase of renewable energy consumption

   o Enhance EMAN framework, to support a more robust and comprehensive
   Energy Efficiency Strategy. Let devices report whatever they can using
   existing interfaces, without waiting until they implement new capabilities
   determined by new or existing standards. Including the capability to
   integrate with external data sources (for example, for devices that don't
   have the capability or reporting any energy-related metrics) such as vendor
   datasheets that provide energy consumption. Use case => upgrading a device
   for better Energy Efficiency Management. Not sure whether framework-related
   requirements should be covered here.

   o Leveraging existing devices modularity to introduce eco-designed components
   in the networks while being able to assess the gains in sustainability.
   https://datatracker.ietf.org/doc/html/draft-stephan-legacy-path-eco-design-01
   https://github.com/emile22/sustainability

   o Discuss the need to reflect component on/off frequency capacity (in YANG)
   to avoid too intensive power on/off.

   o Discuss the need to support a description of the different nature of the
   sources of the energy used (mix). It should be flexible are the types of sources
   might augment in the future.

   o Company's SBTi approved decarbonization plan and how to link it to
   GREEN WG scope, short/mid vs long term.

   The Science Based Targets initiative(SBTi)[https://sciencebasedtargets.org]
   defines and promotes best practice in science-based target setting. Offering
   a range of target-setting resources and guidance, the SBTi independently
   assesses and approves companies targets in line with its strict criteria.

   Open issue, https://github.com/marisolpalmero/GREEN-bof/issues/88

   o Consideration to include in scope, allocate/compute and report the energy
   spent on behalf of a particular customer/user.
   Open issue, marisolpalmero/GREEN-bof#89

# References

## Normative References

   [IEC.61850-7-4]
              International Electrotechnical Commission, "Communication
              networks and systems for power utility automation --
              Part 7-4: Basic communication structure -- Compatible
              logical node classes and data object classes", March 2010.

   [IEC.62053-21]
              International Electrotechnical Commission, "Electricity
              metering equipment (a.c.) -- Particular requirements --
              Part 21: Static meters for active energy (classes 1
              and 2)", January 2003.

   [IEC.62053-22]
              International Electrotechnical Commission, "Electricity
              metering equipment (a.c.) -- Particular requirements --
              Part 22: Static meters for active energy (classes 0,2 S
              and 0,5 S)", January 2003.

   [IEEE-100] IEEE, "The Authoritative Dictionary of IEEE Standards
              Terms, IEEE 100, Seventh Edition", December 2000.

   [IEEE-1621]
              Institute of Electrical and Electronics Engineers,
              "IEEE 1621-2004 - IEEE Standard for User Interface
              Elements in Power Control of Electronic Devices Employed
              in Office/Consumer Environments", 2004.


   [ATIS-0600015.03.2013]
              ATIS, "ATIS-0600015.03.2013: Energy Efficiency for
              Telecommunication Equipment: Methodology for Measurement
              and Reporting for Router and Ethernet Switch Products",
              2013.

   [ETSI-ES-203-136]
              ETSI, "ETSI ES 203 136: Environmental Engineering (EE);
              Measurement methods for energy efficiency of router and
              switch equipment", 2017, <https://www.etsi.org/deliver/
              etsi_es/203100_203199/203136/01.02.00_50/
              es_203136v010200m.pdf>.

   [ITUT-L.1310]
              ITU-T, "L.1310 : Energy efficiency metrics and measurement
              methods for telecommunication equipment", 2020,
              <https://www.itu.int/rec/T-REC-L.1310/en>.

## Informative References

   [IEC.60050] International Electrotechnical Commission, "Electropedia:
   The World's Online Electrotechnical Vocabulary", 2013,
   <http://www.electropedia.org/iev/iev.nsf/ welcome?openform>.

   [ITU-M.3400] International Telecommunication Union, "ITU-T
   Recommendation M.3400 -- Series M: TMN and Network Maintenance:
   International Transmission Systems, Telephone Circuits, Telegraphy,
   Facsimile and Leased Circuits -- Telecommunications Management
   Network - TMN management functions", February 2000.

# Appendix

This appendix should be removed when the initial set of GREEN WG documents will be stable

## Terminology

This section is excepted to move in the GREEN WG draft in charge of terms.
The terms below are a sub set of the whole terminology. There are many other drafts giving additionnal definitions.

   The terms specified in the terminology section are capitalized
   throughout the document; the exceptions are the well-known terms
   "energy" and "power".  These terms are generic and are used in
   generated terms such as "energy-saving", "low-power", etc.

   Embedded carbon (or embodied carbon)

      The total amount of greenhouse gas emissions, measured in tonnes
      of CO2 equivalent (tCO2e), associated with the entire lifecycle
      of a product or material, from raw material extraction through
      manufacturing, transportation, use, and end-of-life disposal or
      recycling.

   Embodied energy

      The total amount of energy consumed in all processes associated
      with the production of a building material or product, from the
      extraction and processing of raw materials, through manufacturing,
      transportation, and installation, to the end of its useful life,
      including disposal or recycling.

   Energy

      Energy is the capacity of a system to do work.  As used by
      electric utilities, it is generally a reference to electrical
      energy and is measured in kilowatt-hours (kWh) [IEEE-100].

   Power

      Power is the time rate at which energy is emitted, transferred, or
      received; power is usually expressed in watts (or in joules per
      second) [IEEE-100].  (The term "power" does not refer to the
      concept of demand, which is an averaged power value.)

   Power Attributes

      Power Attributes are measurements of electric current, voltage,
      phase, and frequencies at a given point in an electrical power
      system (adapted from [IEC.60050]).

      NOTE: Power Attributes are not intended to be "judgmental" with
      respect to a reference or technical value and are independent of
      any usage context.

   Energy Management

      Energy Management is a set of functions for measuring, modeling,
      planning, and optimizing networks to ensure that the network
      elements and attached devices use energy efficiently and in a
      manner appropriate to the nature of the application and the cost
      constraints of the organization [ITU-M.3400].

   Energy Efficiency Management

     Involves deploying and managing network infrastructures with the
     goal of optimizing energy use on network devices while improving
     the overall network utilization.

   Energy Management System

      An Energy Management System is a combination of hardware and
      software used to administer a network with the primary purpose
      being Energy Management.

   Energy Monitoring

      Energy Monitoring is a part of Energy Efficiency Management that
      deals with collecting or reading information from network elements
      and their components to aid in Energy Efficiency Management.

   Energy Control

      Energy Control is a part of Energy Management that deals with
      controlling energy supply and Power State of network elements, as
      well as their components.

   Power Interface

      A Power Interface is an interface at which a device is connected
      to a power transmission medium, at which it can in turn receive
      power, provide power, or both.

   Power Inlet

      A Power Inlet is a Power Interface at which a device can receive
      power from other devices.

   Power Outlet

      A Power Outlet is a Power Interface at which a device can provide
      power to other devices.

   Power State

      A Power State is a condition or mode of a device that broadly
      characterizes its capabilities, power consumption, and
      responsiveness to input [IEEE-1621].

## In Preparation of the GREEN BoF at IETF 120

   The EMAN (Energy MANagement) working group (WG), created in 2010 and now concluded, has produced multiples RFCs

      * RFC7603, Energy Management (EMAN) Applicability Statement

      * RFC7577, Definition of Managed Objects for Battery Monitoring

      * RFC7460, Monitoring and Control MIB for Power and Energy

      * RFC7461, Energy Object Context MIB

      * RFC7326, Energy Management Framework

      * RFC6988, Requirements for Energy Management

      * RFC6933, Entity MIB (Version 4)

   Note also that some other energy-related MIB modules have been created, but not by the EMAN Working Group

      * RFC3433, Entity Sensor MIB module

      * RFC3621, Power Ethernet MIB modules

      * RFC1628, UPS Power Monitoring MIB module

      * LLDP MIB module and LLDP MED MIB module

   Due to limitations regarding Writeable MIB module, one IESG statement published in 2014 encourages the use the NETCONF/YANG standards for configuration. Based on the YANG modules    developments, three MIB  modules (Entity MIB module, Entity Sensor MIB module, Entity State MIB module) have been converted into the "YANG Data Model for Hardware Management" RFC8348.

   However, Power and Energy Monitoring and Control MIB modules has not been converted yet into YANG modules.

   Eleven years after the EMAN requirements RFC 6988 publication, this document re-evaluates the energy-related requirements, as a preparation for the GREEN BoF at IETF 120.

## High-level Differences with RFC6988

The following section will delve into the specific details but from a high level point of view, the differences between this document and the RFC6988 are:

- New definition for "Energy Efficiency Management"

- A focus towards YANG, and not any longer on MIB modules

- As a consequence from the previous point, the ENTITY-MIB v4 RFC6933 is replaced by the Hardware YANG module RFC8348

- battery management is removed (as batteries haves some self-optimization features these days). Nevertheless 'Battery' will appear as a source of power of a type of backup

- Less focus on the Power over Ethernet management, Nevertheless Reporting on Other Entities remains an open issue

- A focus on reporting lifecycle management, considering energy and transformation towards carbon awareness
