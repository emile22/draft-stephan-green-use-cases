---
title: "Use Cases for Energy Efficiency Management"
abbrev: "Use Cases for Energy Efficiency"
docname: draft-stephan-green-use-cases-latest
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
  github: "emile22/draft-stephan-green-use-cases"
  latest: "https://emile22.github.io/draft-stephan-green-use-cases/draft-stephan-green-use-cases.html"

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
  -
    fullname: Carlos J. Bernardos
    org: Universidad Carlos III de Madrid
    email: cjbc@it.uc3m.es

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

--- abstract

This document groups use cases for Energy efficiency Management of network devices.

Discussion Venues

Source of this draft and an issue tracker can be found at https://github.com/emile22/draft-stephan-green-use-cases

--- middle

# Introduction

This document groups use cases collected from operators and from discussions since the GREEN WG preparations.

It provides a set of use cases for Energy efficiency Management of network devices. The scope is devices like switches, routers, servers and storage devices having an IP address providing a management interface. It includes their built-in components that receive and provide electrical energy.

In annex we recall the framework where the use cases can be put in situation.

# Use Cases

This section describes a number of relevant use cases with the purpose of elicit requirements for Energy Efficiency Management.
This is a work in progress and additional use cases will be documented in next versions of this document. Use cases which are not tied enough to the current GREEN chater will be moved to the GREEN WG wiki pages or to other WGs or RGs.

## Incremental Application of the GREEN Framework {#incremental-use-case}

### Use Case Description
This section describes an incremental example [legacy-path] of usage showing how a product, a service and a network can use the framework in different settings.

This use case is the less trendy of all the use cases by far as its ambitious is limited to migration and coexistence, as usual. Nevertheless from a telco perspective, it is the centrality for 2 main reasons:

- to start immediatly the move to energy efficiency using legacy devices;
- to account the gain of energy efficiency during incremental deployment of energy efficient network components;

Legacy routers, equipped with traditional Ethernet ports and optical interfaces will continue to operate within the network. As part of broader sustainability and energy efficiency goals, there is interest in exploring the incremental integration of such devices into energy efficiency framework deployments.

Two directions are considered:

- Improving energy efficiency of legacy devices through targeted upgrades—such as replacing line cards, optimizing firmware behavior, or reconfiguring interface usage based on operational demand.

- Including legacy devices in early phases of energy-aware system deployment, ensuring that improvements are not limited only to new hardware generations.

Legacy devices can still contribute to reducing overall power consumption and lowering resource usage and associated environmental impact. Supporting these incremental improvements helps bridge the gap between existing infrastructure and modern energy-aware network strategies.

Device moving gradually to GREEN energy efficiency supports:

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

### GREEN WG Charter Specifics
This use case demonstrates how Energy Efficiency can be incrementally applied and measured in legacy networks.

### The Need for Energy Efficiency
Ensures that energy efficiency can be deployed, operated and measured per components, without waiting for full infrastructure upgrades.

### Requirements for GREEN WG
- Baseline Measurement: Ability to establish reference energy usage per device (from datasheets or monitoring).
- Component-Level Upgradability: Support partial migration of device subsystems to GREEN-aware models.
- Legacy Compatibility: Ensure the framework can include legacy equipment alongside GREEN-enabled devices.
- Energy Saving Validation: Mechanisms to measure and verify actual energy savings over time.
- Protection from Overuse: Avoid frequent power cycling that may damage sensitive components like lasers or connectors.

## Selective reduction of energy consumption in network parts proportional to traffic levels

### Use Case Description
Traffic levels in a network follow patterns reflecting the behavior of consumers. Those patterns show periodicity in the terms of the traffic delivered, that can range from daily (from 00:00 to 23:59) to seasonal (e.g., winter to summer), showing peaks and valleys that could be exploited to reduce the consumption of energy in the network proportionally, in case the underlying network elements incorporate such capabilities. The reduction of energy consumption could be performed by leveraging on sleep modes in components up to more extreme actions such as switching off network components or modules. Such decisions are expected to no impact on the service delivered to customers, and could be accompanied by traffic relocation and / or concentration in the network.

### GREEN WG Charter Specifics
This use case fits within the GREEN WG’s objectives by emphasizing energy-aware operational adjustments across network infrastructure that optimize energy use based on traffic loads and the intelligent activation/deactivation of resources.

### The Need for Energy Efficiency
Reducing energy usage during during low-demand periods can lower operational costs and carbon emissions while also prolonging equipment lifespan.

### Requirements for GREEN WG

- Support for device and component-level sleep, standby, and hibernation modes.
- Component-level control (e.g., ports, modules).

## Reporting on Lifecycle Management

### Use Case Description
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

### GREEN WG Charter Specifics
Capture lifecycle energy data and integrate it with operational metrics.

### The Need for Energy Efficiency
Considering energy from production to disposal supports the broader goal of reducing total environmental impact.

### Requirements for GREEN WG
- Awareness of backup systems (e.g., batteries, generators).
- Data ingestion from vendor databases or datasheets.

## Real-time Energy Metering of Virtualised or Cloud-native Network Functions

### Use Case Description

Cloud-native and virtualized functions require precise real-time energy measurements to manage their dynamic workloads and infrastructure efficiently.
Effective metering of virtualized network infrastructure is critical for the efficient management and operation of next-generation mobile networks [GREEN_NGNM].

### GREEN WG Charter Specifics
// TODO.

### The Need for Energy Efficiency
// TODO.

### Requirements for GREEN WG
// TODO.

## Indirect Energy Monitoring and control

### Use Case Description
There are cases where Energy Management for some devices need to report on other entities. There are two major
   reasons for this.

   o  For monitoring energy consumption of a particular entity, it is not always sufficient to
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

### GREEN WG Charter Specifics
// TODO.

### The Need for Energy Efficiency
// TODO.

### Requirements for GREEN WG
// TODO.

## Consideration of other domains for obtention of end-to-end metrics

### Use Case Description
The technologies under the scope of IETF provide the necessary connectivity to other technological domains. For the obtention of metrics end-to-end it would be required to combine or compose the metrics per each of those domains.

An exemplary case is the one of a network slice service. The concept of network slice was initially defined by 3GPP {{TS23.501}}, and it has been further extended to the concerns of IETF {{?RFC9543}}.

In regards energy efficiency, 3GPP defines a number of energy-related key performance indicators (KPI) in {{TS28.554}}, specifically Energy Efficiency (EE) and Energy Consumption (EC) KPIs. There are KPIs particular for a slice supporting a specific kind of service (e.g., Mobile Broadband or MBB), or generic ones, like Generic Network Slice EE or Network Slice EC. Assuming these as the KPIs of interest, the motivation of this use case is the obtention of the equivalent KPIs at IETF level, that is, for the network slice service as defined in {{?RFC9543}}.

Note that according to {{TS28.554}}, the Generic Network Slice EE is the performance of the network slice divided by the Network Slice EC. Same approach can be followed at IETF level. Note that for avoiding double counting the energy at IETF level in the calculation of the end-to-end metric, the 3GPP metric should only consider the efficiency and consumption of the 3GPP-related technologies.

### GREEN WG Charter Specifics
// TODO.

### The Need for Energy Efficiency
// TODO.

### Requirements for GREEN WG
// TODO.

## Dynamic adjustment of network element throughput according to traffic levels in wireless transport networks

### Use Case Description
Radio base stations are typically connected to the backbone network by means of fiber or wireless transport (e.g., microwave) technologies. In the specific case of wireless transport, automation frameworks have been defined {{ONF-MW}}{{?RFC8432}}{{mWT025}} for their control and management.

One of the parameters subject of automated control is the power of the radio links. The relevance of that capability is that the power can be adjusted accordingly to the traffic observed. Wireless transport networks are typically planned to support the maximum traffic capacity in their area of aggregation, that is, the traffic peak. With that input, the number of radio links in the network element and the corresponding power per radio link (for supporting a given modulation and link length in the worst weather conditions) are configured. This is done to avoid any kind of traffic loss in the worst operational situation. However, such operational needs are sporadic, giving room for optimization during normal operational circumstances and/or low traffic periods.

Power-related parameters are for instance defined in {{?RFC8561}}. Those power parameters can be dynamically configured to adjust the power to the observed traffic levels with some coarse granularity, but pursuing certain degrees of proportionality.

### GREEN WG Charter Specifics
// TODO.

### The Need for Energy Efficiency
// TODO.

### Requirements for GREEN WG
// TODO.

## Video streaming use case

### Use Case Description
Video streaming is nowadays the major source of traffic observed in ISP networks, in a propotion of 70% or even higher. Over-the-top distribution of streaming traffic is typically done by delivering a unicast flow per end user for the content of its interest.In consequence, during the hours of higher demand, the total traffic in the network is proportional to the concurrence of users consuming the video streaming service. The amount of traffic is also dependent of the resolution of the encoded video (the higher the resolution, the higher the bit rate per video flow), which tends to be higher as long as the users devices support such higher resolutions.

The consequence of both the growth in the number of flows to be supported simultaneously, and the higher bit rate per flow, is that the nework elements in the path between the source of the video and the user have to be dimensioned accordingly. This implies the continuous upgrade of those network elements in terms of capacity, with the need of deploying high-capacity network elements and components. Apart from the fact that this process is shortening the lifetime of network elements, the need of high capacity interfaces also increase the energy consumption (despite the effort of manufacturers in creating more efficient network element platforms). Note that nowadays there is no actual possibility of activating energy consumption proportionality (in regards the delivered traffic) to such network elements.

As a mean of slowing down this cycle of continuos renewal, and reduce the need og higher bit rate interfaces / line cards, it seems convenient to explore mechanisms that could reduce the volume of traffic without impacting the user service expectations. Variants of multicast or different service delivery strategies can help to improve the energy efficiency associated to the video streaming service. It should be noted that another front for optimization is the one related to the deployment of cache servers in the network.

### GREEN WG Charter Specifics
// TODO.

### The Need for Energy Efficiency
// TODO.

### Requirements for GREEN WG
// TODO.

## WLAN Network Energy Saving

### Use Case Description
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

### GREEN WG Charter Specifics
// TODO.

### The Need for Energy Efficiency
// TODO.

### Requirements for GREEN WG
// TODO.

## Fixed Network Energy Saving

### Use Case Description
Traffic on the Tidal network has an obvious tidal period, including heavy-traffic periods and light-traffic periods: The time duration of heavy traffic load and light traffic load are clearly distinguished.
The switching time between the heavy-traffic period and the light-traffic period is quite fixed and cyclic.
In a tidal network, some network devices can be shut down or sleep during low-traffic periods to save energy.
In the metro or backbone network, the routers support various different speed interfaces, e.g., the gigabit level to 10GE/50GE, or 100G to 400G. Routers might choose to adjust speed of the interface or downgrade from high speed interface to low speed interface based on network traffic load changes to save the energy.
In addition, the routers can adjust the number of working network processor cores and clock frequency of chipsets and the number of SerDes buses based on network traffic load changes to save the energy.

### GREEN WG Charter Specifics
// TODO.

### The Need for Energy Efficiency
// TODO.

### Requirements for GREEN WG
// TODO.

## Energy Efficiency Network Management

### Use Case Description
Network level Energy Efficiency allows network operators not only see real time energy consumption in the network devices of large scale network, but also
allow you see
o which network devices enable energy saving, which devices not,which are legacy ones,
o The total energy consumption changing trend over the time of the day, for all network devices,
o Energy efficiency changing trend over the time of the day for the whole network.
With the better observability to energy consumption statistics data and energy efficiency statistics data, the network operators can know which part of the network need to be adjusted or optimized based on network status change.

### GREEN WG Charter Specifics
// TODO.

### The Need for Energy Efficiency
// TODO.

### Requirements for GREEN WG
// TODO.

## ISAC-enabled Energy-Aware Smart City Traffic Management

### Use case description

Integrated Sensing and Communications (ISAC) is emerging as a key
enabler for next-generation wireless networks, integrating sensing
and communication functionalities within a unified system.  By
leveraging the same spectral, hardware, and computational resources,
ISAC enhances network efficiency while enabling new capabilities such
as high-resolution environment perception, object detection, and
situational awareness.  This paradigm shift is particularly relevant
for applications requiring both reliable connectivity and precise
sensing, such as autonomous vehicles, industrial automation, and
smart city deployments.  Given its strategic importance, ISAC has
gained significant traction in standardization efforts.  The ETSI
Industry Specification Group (ISG) on ISAC has been established to
explore technical requirements and use cases, while 3GPP has
initiated discussions on ISAC-related features within its ongoing
research on future 6G systems.  Furthermore, research initiatives
within the IEEE and IETF are investigating how ISAC can be integrated
into network architectures, spectrum management, and protocol design,
making it a critical area of development in the evolution of wireless
networks.

This use case involves deploying ISAC systems in a smart city to
monitor and optimize vehicles' traffic flows while minimizing energy
consumption of the mobile network.  The system integrates sensing
technologies, such as radar and LIDAR, with communication networks to
detect vehicle density, monitor road conditions, and communicate with
autonomous vehicles or traffic lights.  By using ISAC, the system
minimizes redundant infrastructure (e.g., separate sensors and
communication equipment), thus reducing the overall carbon and energy
footprint.

### GREEN WG Specifics

Energy Consumption Monitoring: Each ISAC component (e.g., roadside
units, integrated sensors, and communication transceivers) is capable
of reporting its energy consumption in real time to the centralized
or distributed energy management system.

Reconfiguration for Energy Efficiency: The system can dynamically
switch between high-resolution sensing modes (e.g., during peak
hours) and low-power modes (e.g., during low traffic periods).  The
network can reconfigure traffic communication paths to prioritize
routes or nodes that consume less power, leveraging energy-efficient
communication protocols.

Integration of Local and Global Energy Goals: The system can operate
both locally (e.g., turning off specific roadside units in low-
traffic areas) and globally (e.g., modifying traffic patterns across
the city) to achieve defined energy consumption goals.

### Requirements for GREEN WG

1. Measurement Granularity:

  - Ability to measure energy consumption per ISAC component (e.g., roadside unit, sensor, transceiver).
  - Granular reporting per communication link or sensing mode (e.g., high-power radar mode vs. low-power mode).

2. Power Control Mechanisms:

  - Ability to switch components on/off or place them in sleep/standby mode when not in use.
  - Support for dynamic adjustment of sensing resolution or communication bandwidth to balance energy savings and system performance.

3. Reconfiguration and Adaptability:

  - Support for hardware reconfiguration (e.g., adaptive sensing modes, transceiver settings) to optimize energy use.
  - Mechanisms to steer traffic or adjust network routing based on global or local energy-saving objectives.

4. Global Coordination:

  - Capabilities for cross-domain coordination to enable global optimization (e.g., city-wide traffic rerouting or dynamic resource allocation across different regions).
  - Ability to aggregate and analyze energy consumption data from all ISAC components to inform high-level decision-making.

5. Energy-Aware Standards and Protocols:

   - Communication protocols that minimize power usage while maintaining reliability.
   - Interoperability standards for energy-aware reconfiguration across heterogeneous ISAC components and systems.

## Double Accounting Open issue

### Use case description
Energy consumption monitoring often includes metering at both upstream and downstream levels of power distribution. While this can provide granular visibility, it may also lead to double accounting if not carefully managed.

A common case arises when energy is measured at the input of a Power Delivery Unit (PDU), and individually at each device powered by that PDU (e.g., servers, switches). Since the PDU input already reflects the downstream consumption, summing the per-device values with the PDU input results in redundant reporting.
A similar issue occurs with Power over Ethernet (PoE) infrastructures when a network switch supply power directly to devices. If the total power consumption measured encompasses both the power delivered to the PoE switch and to the powered devices, this again results in double accounting.

These 2 cases distort energy dashboards and indicators such as Power Usage Effectiveness (PUE).

### GREEN WG Charter Specifics
Unlike most of the WGs, the GREEN WG purpose sums the constraints of data networks and grid/off-grid networks, independantly of the location of the network domain in the architecture (aka edge, core...):
- include the grid network picture in networks operation

### The Need for Energy Efficiency
// TODO.

### Requirements for GREEN WG
The monitoring must not count twice the power that passthru devices and components monitored, including legacy elements.

## Energy Efficiency Under Power Shortage

### Use case description

This use case focuses on network devices (e.g., routers, switches, access points) that must maintain essential connectivity during power shortages.
Telecom locations use different power backups levels (as example battery, standby generator ...). Devices may have access to one or more backup power sources such as onboard batteries, PoE fallback, or centralized UPS systems. When a power shortage occurs, the network device transitions from grid power to available backup sources and must prioritize operational resilience over typical energy optimization strategies. Unlike behavior in a normally powered state, the focus here is not on minimizing energy consumption per se, but on sustaining essential operation with limited energy and prepare to worse situations and more constrained powered state fallbacks. These behaviors increase the device’s ability to operate longer under backup power, ensuring availability of essential services during outages.

Data networks and grid networks resiliency are closely interleaved during power shortage. It is a race between the speed of the operations to restore the grid network and the availability of mobile connectivity for power grid repair teams because of the impairment of operational visibility and response coordination.

Network constraints differ in sparse or dense situations but shortage impacts change accordingly. This is becoming crucial and not limited to sparse environments where stable power supply is well known to not be guaranteed: it applies to dense cities' utilities which operations are coupled to the simoultaneous availability of both power and persistent data communication and compute at the edge.

### GREEN WG Charter Specifics
Unlike most of the WGs, the GREEN WG purpose sums the constraints of data networks and grid/off-grid networks, independantly of the location of the network domain in the architecture (aka edge, core...):
- Improved networks resiliency by making energy constraints an input into the network's operations.

### The Need for Energy Efficiency
Energy efficiency under power shortage conditions is fundamentally different from routine energy optimization. In this context, energy is a finite and rapidly depleting resource, not just an environmental concern or cost factor:
- Optimize backup power usage for resilience
- Maintain critical networking capabilities during power shortage events
- Maximize operational uptime using fallback power sources

### Requirements for GREEN WG
- Awareness of backup systems (e.g., batteries, generators).
- Awareness of hierarchical fallback to more constrained powered state.

# Security Considerations

Energy efficiency management comes with numerous security considerations :

   Controlling Power State and power supply of entities are considered
   highly sensitive actions, since they can significantly affect the
   operation of directly and indirectly connected devices.  Therefore,
   all control actions must be
   sufficiently protected through authentication, authorization, and
   integrity protection mechanisms.

   Entities that are not sufficiently secure to operate directly on the
   public Internet do exist and can be a significant cause of risk, for
   example, if the remote control functions can be exercised on those devices from anywhere on the Internet.

   The monitoring of energy-related quantities of an entity as addressed
   can be used to derive more information than
   just the received and provided energy; therefore, monitored data
   requires protection.  This protection includes authentication and
   authorization of entities requesting access to monitored data as well
   as confidentiality protection during transmission of monitored data.
   Privacy of stored data in an entity must be taken into account.
   Monitored data may be used as input to control, accounting, and other
   actions, so integrity of transmitted information and authentication
   of the origin may be needed.

# IANA Considerations

This document has no IANA actions.

# Acknowledgments

The contribution of Luis M. Contreras to this document has been supported by the Smart Networks and Services Joint Undertaking (SNS JU) under the European Union's Horizon Europe research and innovation projects 6Green (Grant Agreement no. 101096925) and Exigence (Grant Agreement no. 101139120).

# Use Cases Living List

   Consider 5g vs network slicing: 3GPP spec describing energy efficiency KPIs. 3GPP TS 28.554. Reference:https://datatracker.ietf.org/doc/rfc9543/
   Connectivity from radio side (trying to control the traffic/related work to CCAMP)
   Marisol to add one use case: drift from data specifications... (somehow link to the above)
   Energy Metric in E2E view

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
   <http://www.electropedia.org/iev/iev.nsf/welcome?openform>.

   [ITU-M.3400] International Telecommunication Union, "ITU-T
   Recommendation M.3400 -- Series M: TMN and Network Maintenance:
   International Transmission Systems, Telephone Circuits, Telegraphy,
   Facsimile and Leased Circuits -- Telecommunications Management
   Network - TMN management functions", February 2000.

# Appendix 1, Template preparation

This appendix should be removed when the template will be stable.

It is based on the example from https://datatracker.ietf.org/doc/rfc9450/.

## Use Case Description
General description of the use case.

## GREEN WG Charter Specifics
(if there are no GREEN specific aspects, then it is not a UC to be documented)
For example, the use case involves components that can report on energy consumption and that might be reconfigured (on a local or global scale) to operate based on energy goals/limitations.
### The Need for Energy Efficiency

## Requirements for GREEN
Examples (can be split into different categories to facilitate a summary at the end of the document):
- Granularity of measurements should be per component, per line, per port…
- Ability to switch on/off, put on sleep mode… components.
- Ability to reconfigure hardware mode based on power savings (e.g., reduce reliability or speed).
- Ability to operate globally (not constrained to just one device) based on power savings/goals (e.g., steer traffic using a different path that consumes less energy)



