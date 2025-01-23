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

In annex we recall the framework where the use cases can be put in situation using three core functions: discovery, monitoring, and control.

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

(i) Avoid a power-on/power-off frequency to break component parts (aka laser, power parts, wire connectors ...)

(ii) the gain must be measurable

(iii) network-wide energy efficiency solutions must include legacy devices and green-wg ready devices

## Selective reduction of energy consumption in network parts proportional to traffic levels

Traffic levels in a network follow patterns reflecting the behavior of consumers. Those patterns show periodicity in the terms of the traffic delivered, that can range from daily (from 00:00 to 23:59) to seasonal (e.g., winter to summer), showing peaks and valleys that could be exploited to reduce the consumption of energy in the network proportionally, in case the underlying network elements incorporate such capabilities. The reduction of energy consumption could be performed by leveraging on sleep modes in components up to more extreme actions such as switching off network components or modules. Such decisions are expected to no impact on the service delivered to customers, and could be accompanied by traffic relocation and / or concentration in the network.

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

## Fixed Network Energy Saving

Traffic on the Tidal network has an obvious tidal period, including heavy-traffic periods and light-traffic periods: The time duration of heavy traffic load and light traffic load are clearly distinguished.
The switching time between the heavy-traffic period and the light-traffic period is quite fixed and cyclic.
In a tidal network, some network devices can be shut down or sleep during low-traffic periods to save energy.
In the metro or backbone network, the routers support various different speed interfaces, e.g., the gigabit level to 10GE/50GE, or 100G to 400G. Routers might choose to adjust speed of the interface or downgrade from high speed interface to low speed interface based on network traffic load changes to save the energy.
In addition, the routers can adjust the number of working network processor cores and clock frequency of chipsets and the number of SerDes buses based on network traffic load changes to save the energy.

## Energy Efficiency Network Management

Network level Energy Efficiency allows network operators not only see real time energy consumption in the network devices of large scale network, but also
allow you see
o which network devices enable energy saving, which devices not,which are legacy ones,
o The total energy consumption changing trend over the time of the day, for all network devices,
o Energy efficiency changing trend over the time of the day for the whole network.
With the better observability to energy consumption statistics data and energy efficiency statistics data, the network operators can know which part of the network need to be adjusted or optimized based on network status change.

# Security Considerations

Resiliency is an implicit use case of energy efficiency management which comes with numerous security considerations :

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

# Appendix

This appendix should be removed when the initial set of GREEN WG documents will be stable

## Framework Discussed During the BoF {#framework}

The framework is maintainded in this version of the draft. It will be removed when the use cases descriptions will be mature.

Discovery functions involve identifying energy-managed networks, devices, and their components, as well as discovering the inventory of power components capabilities, optimization control capabilities, and nominal condition use. Monitoring functions encompass tracking power states, power attributes, energy consumption, network performance, and energy efficiency metrics. Control functions include managing energy-saving and optimization functions and the power states of energy-managed devices and their components.

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
