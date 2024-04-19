DSA-2000 Document No. 00003

Concept of Operations

Katie Jameson, Vanessa Moss, Casey Law, Martin Pokorny, Rick Hobbs, Greg
Hellbourg, Steven Myers, James Lamb and Francois Kapp

California Institute of Technology

+-----------------------------------------------------------------------+
| +--------------------------------+--------------------------------+   |
| | Version:                       | 1                              |   |
| +--------------------------------+--------------------------------+   |
| | Version date:                  | 2023-12-17                     |   |
| +--------------------------------+--------------------------------+   |
| | Original date:                 | 2023-01-06                     |   |
| +--------------------------------+--------------------------------+   |
| | Controlled document:           | Yes                            |   |
| +--------------------------------+--------------------------------+   |
| | WBS Level 2:                   | PRJ--Project                   |   |
| +--------------------------------+--------------------------------+   |
| | Document type:                 | MGT--Management                |   |
| |                                |                                |   |
| |                                | Management                     |   |
| +--------------------------------+--------------------------------+   |
+=======================================================================+
|   ------------------------------------------------------------------- |
|                  **Name**          **Signature (PDF)**    **Date**    |
|   -------------- ----------------- ---------------------- ----------- |
|   **PI**                                                              |
|                                                                       |
|   **Subsystem                                                         |
|   Lead**                                                              |
|                                                                       |
|   **Project                                                           |
|   Engineer**                                                          |
|                                                                       |
|   **Project                                                           |
|   Manager**                                                           |
|   ------------------------------------------------------------------- |
+-----------------------------------------------------------------------+

Revision History

+----+----------+------------+-----------------------+----------------+
| ** | **Date** | **Sections | **Reasons / Remarks** | **Author(s)**  |
| Ve |          | Affected** |                       |                |
| r. |          |            |                       |                |
| ** |          |            |                       |                |
+====+==========+============+=======================+================+
| 0. | 20       | All        | Original              |                |
| 01 | 23-01-06 |            |                       |                |
|    |          | All        | Development for PDR   |                |
| 0. | 20       |            |                       |                |
| 02 | 23-10-20 | All        | Post PDR minor        |                |
|    |          |            | updates               |                |
| 1  | 20       | All        |                       |                |
|    | 23-12-17 |            | Added user stories, a |                |
| 2  |          |            | day in the life,      |                |
|    | TBD      |            | cross-referencing and |                |
|    |          |            | requirements table    |                |
+----+----------+------------+-----------------------+----------------+

#   {#section .TOC-Heading}

# Table of Contents {#table-of-contents .TOC-Heading}

[1 Introduction [6](#introduction)](#introduction)

[2 Array Operations Concept
[6](#array-operations-concept)](#array-operations-concept)

[2.1 Automated Scheduling
[6](#automated-scheduling)](#automated-scheduling)

[2.1.1 Sky coverage and tiling
[7](#sky-coverage-and-tiling)](#sky-coverage-and-tiling)

[2.1.2 Array safety considerations
[7](#array-safety-considerations)](#array-safety-considerations)

[2.1.3 Management of survey progress
[8](#management-of-survey-progress)](#management-of-survey-progress)

[2.1.4 Simulation plans [9](#simulation-plans)](#simulation-plans)

[2.2 Human involvement in operations
[9](#human-involvement-in-operations)](#human-involvement-in-operations)

[2.3 Data Quality Assurance
[10](#data-quality-assurance)](#data-quality-assurance)

[2.3.1 Preventative data quality assurance
[10](#preventative-data-quality-assurance)](#preventative-data-quality-assurance)

[2.3.2 Reactive data quality assurance
[10](#reactive-data-quality-assurance)](#reactive-data-quality-assurance)

[2.3.3 Links with Collaborative Intelligence
[11](#links-with-collaborative-intelligence)](#links-with-collaborative-intelligence)

[2.4 Software and Service Management
[11](#software-and-service-management)](#software-and-service-management)

[2.4.1 Software management
[11](#software-management)](#software-management)

[2.4.2 Service management
[12](#service-management)](#service-management)

[2.5 Data Management [12](#data-management)](#data-management)

[2.5.1 Radio Camera Processor data management
[12](#radio-camera-processor-data-management)](#radio-camera-processor-data-management)

[2.5.2 On-Site data management
[12](#on-site-data-management)](#on-site-data-management)

[2.5.3 Off-Site data management
[13](#off-site-data-management)](#off-site-data-management)

[2.5.4 Configuration Management
[13](#configuration-management)](#configuration-management)

[2.6 Security [13](#security)](#security)

[2.6.1 Cybersecurity [13](#cybersecurity)](#cybersecurity)

[3 Array Maintenance Concept
[13](#array-maintenance-concept)](#array-maintenance-concept)

[3.1.1 Installation and tracking of antennas
[14](#installation-and-tracking-of-antennas)](#installation-and-tracking-of-antennas)

[3.1.2 Determination of MTBF and MTTR
[14](#determination-of-mtbf-and-mttr)](#determination-of-mtbf-and-mttr)

[3.1.3 Operational impact of antennas under maintenance
[14](#operational-impact-of-antennas-under-maintenance)](#operational-impact-of-antennas-under-maintenance)

[3.1.4 ML/AI for planning and scheduling maintenance
[14](#mlai-for-planning-and-scheduling-maintenance)](#mlai-for-planning-and-scheduling-maintenance)

[3.1.5 Logistics support [15](#logistics-support)](#logistics-support)

[3.1.5.1 Antenna Maintenance
[15](#antenna-maintenance)](#antenna-maintenance)

[3.2 Internal/External Communication and Troubleshooting
[15](#internalexternal-communication-and-troubleshooting)](#internalexternal-communication-and-troubleshooting)

[3.3 Antenna Access Plan
[16](#antenna-access-plan)](#antenna-access-plan)

[4 Site Infrastructure Concept
[16](#site-infrastructure-concept)](#site-infrastructure-concept)

[4.1 Array Infrastructure Concept
[16](#array-infrastructure-concept)](#array-infrastructure-concept)

[4.2 Computer Infrastructure
[16](#computer-infrastructure)](#computer-infrastructure)

[4.2.1 Backups [17](#backups)](#backups)

[4.3 Site Buildings [17](#site-buildings)](#site-buildings)

[4.3.1 Control Building (Building 1)
[17](#control-building-building-1)](#control-building-building-1)

[4.3.2 Maintenance Building (Building 2)
[18](#maintenance-building-building-2)](#maintenance-building-building-2)

[4.3.3 Accommodation Building (Building 3)
[18](#accommodation-building-building-3)](#accommodation-building-building-3)

[4.4 Vehicles and Fuel [18](#vehicles-and-fuel)](#vehicles-and-fuel)

[4.5 Power [18](#power)](#power)

[4.6 Water [19](#water)](#water)

[4.7 On-Site Communications
[19](#on-site-communications)](#on-site-communications)

[5 RFI Monitoring [19](#rfi-monitoring)](#rfi-monitoring)

[6 On-site safety [20](#on-site-safety)](#on-site-safety)

[7 Off-site Infrastructure Concept
[20](#off-site-support-infrastructure-concept)](#off-site-support-infrastructure-concept)

[8 Transition from Commissioning to Operations
[21](#transition-from-commissioning-to-operations)](#transition-from-commissioning-to-operations)

[9 Community Engagement Concept
[21](#community-engagement-concept)](#community-engagement-concept)

[10 Acronyms [22](#acronyms)](#acronyms)

Abstract

DSA-2000 will be an array of considerable scale and complexity,
representing a large leap forward in next-generation radio telescope
instrumentation. Given this, the requirements associated with the
operations, maintenance, site infrastructure and general management of
the array are similarly distinct from previous and current operational
facilities worldwide. This document captures and describes the concept
of operations envisaged for DSA-2000 based on these requirements,

# Introduction 

In this document, we outline the current concepts related to how the
DSA-2000 array will operate and be maintained. With 2048 antennas spread
over a 19 km x 15 km area, the operations concept needs to be well
thought out to maximize efficiency and minimize staffing requirements.

At this initial stage, we also identify key assumptions or questions
that will need to be verified or determined before a full model of
operations can be developed and adopted.

# Array Operations Concept 

The DSA-2000 project is primarily focused on carrying out pre-planned
science surveys. The only planned departure from routine observations
and maintenance would be for Targets of Opportunity (ToO) and Director's
Discretionary Time (DDT). A critical part of the system will be the
development of smart automated scheduler and a monitor and control
system that are both designed to require minimal human intervention.

In general, once the array is commissioned, it will be continuously
observing -- performing the cadenced survey. Maintenance and repairs
will be carried out during observations, usually affecting a small
fraction of the capabilities. Exceptions to this may occur, for example
if a major single point failure occurs, such as the failure of the site
uninterruptable power supply (UPS). As much as is possible, single-point
failures will have mitigation plans, for example by way of redundant hot
and/or cold spares. For failures that affect part of the system, modular
line-replaceable units (LRU) will allow quick recovery. LRUs will be
either hot-swappable or able to be powered down without affecting any
other part of the system.

On-site staff will perform maintenance tasks daily during the week,
while at least one person off site will be assigned to monitor the
performance of the system and coordinate on-site daily tasks, including
scheduling repairs that are not part of the routine maintenance task
list.

The science requirements call for 97% of the collecting area and 65% of
the total band to be available more than 80% of the time. Conversely,
the array is deemed to be fully available with 97% of the collecting
area and 65% of the band capable of being processed through the entire
system. The collecting area/bandwidth availability can be extended to
other subsystem, for example, failure of an RCF node will remove one
antenna, while failure of an RCP node will remove part of the band. More
complex failure trees will be developed during the Final Design Phase to
refine the availability model.

## Automated Scheduling 

DSA-2000 will focus on conducting large-scale surveys of the sky for 65%
of its on-sky time, alongside other survey components including pulsar
surveys and reactive time-critical observations. Given the fixed nature
of much of this observing, an automated scheduling system will be
adopted in order to maximize the efficiency of the array. As well as
handling the main survey observations, the scheduler will also need to
account for planned and unplanned interruptions such as maintenance and
ToO/DDT observations.

The intent is for this automated scheduler to be robust, autonomous,
dynamic, reactive, deterministic, communicative and transparent, as
defined below:

**Robust:** able to be trusted with reliably and effectively making
appropriate scheduling decisions that are comparable to the
decision-making processes of equivalent human operators

**Autonomous**: capable of making decisions without direct human input
in the majority of cases, unless human oversight or collaboration is
required (e.g. in the case of safety of the system)

**Dynamic**: designed to make decisions about what to observe next based
on its understanding of the current environmental conditions, live
system constraints, content of the observation pool, required sky/field
constraints and a series of weightings which determine priority

**Reactive**: able to react to changing conditions (e.g. weather,
hardware failure, etc) and change course in an appropriate way at all
hours of the day to maximize science output and data quality

**Deterministic**: given the same initial conditions and system status,
the scheduler will make the same decision in each case, ensuring
decisions are explicable and predictable given constraints

**Communicative**: notifies relevant people as appropriate as part of
standard operational workflows or in the case of issues requiring human
attention or expertise in order to resolve

**Transparent:** via appropriate interfaces, the decisions made by the
scheduler are logged and able to be understood by human experts, who in
the ideal case can contribute to improving or adjusting the
decision-making process of the scheduler as required

It is expected that there will be a base level of scheduling control
which involves submitting a parameter set of variables that specify the
system setup for a given observation, including parameters such as the
frequency setup, field coordinates, constraints, etc. This low-level
scheduling control will be communicated with by the autonomous
scheduler, but can also be interfaced with by other means of controlling
the system (e.g. more manual specification of observations). This
enables flexibility in telescope control, which will be required
particularly early on during commissioning or in cases where a
particular mode of operation has not yet been integrated into the
autonomous scheduler.

An overall architecture for the scheduler will be prepared prior to the
start of construction, capturing the flow of operations that the
scheduler will follow as well as outlining the expected features and
modules it will need to contain. This design will be flexible as much as
possible to ensure that future identified requirements can be
incorporated into the scheduler over time, given the high likelihood
that commissioning may shift any assumptions made prior to live
operations of the system. The overall control of the system will be an
evolving process from highly manual (in the very early stages of
commissioning) to semi-automated (human control in collaboration with
the improving scheduler) to fully autonomous (where the scheduler is
primarily responsible for operating the system).

### Sky coverage and tiling

DSA-2000 will primarily spend its time mapping the visible sky. The
field list covering the sky is expected to be \~8700 pointings which are
grouped into a tiered hierarchy determining which fields will be
mosaicked together at the processing stage. It is anticipated that
fields will be treated individually during the scheduling
decision-making process, with a prioritization scheme in place to
greatly increase the priority of fields that are located within the same
tile or neighboring tiles which share edges, but an approach where tiles
are instead scheduled (including scans of their associated fields) will
also be considered. Each tile is currently planned to be roughly 5 x 5
deg in size, with \~25 fields within a given tile, taking an estimated
\~5 hr to be completely observed.

### Array safety considerations

The automated scheduler will act essentially as a proxy for a human
operator, and thus will (as much as possible) not take direct
responsibility for the safety of the array or associated hardware.
Instead, safety controls will be in place at several layers: e.g. local
control which overrides remote control (for example, in the case of
local antenna maintenance), hardware controls/limits which oversee
safety of equipment directly, software controls/limits which provide a
back-up measure of safety and finally the scheduler, which will be able
to access an overview of the current system and environmental status to
aid with making decisions regarding scheduling.

As such, the primary control for safety will sit with the domain of
monitoring and control, and the scheduler will act as a secondary
control/back-up. For example: in the case of strong winds or bad
weather, the array should automatically stow based on system-level
thresholds and alerts, but these alerts should also be visible to the
scheduler which then can access them and choose not to attempt
scheduling until the alerts have returned to normal. In the case of the
scheduler attempting to schedule, the system would intervene/override
and error any attempted observations to preserve the safety of the
array.

Another example would be limiting power usage in winter (especially at
night), given that the array is expected to rely heavily on solar power.
The scheduler can be made aware of this logic via control system
variables and alerts (e.g., "power-saving mode active"), but should not
be primarily responsible for the actions that need to be taken on the
hardware side to preserve the safety of the array. The scheduler *can*
be made aware of how its decision-making process should change given
this state (if that is a factor to consider) but would only be reacting
to such a power-saving mode rather than controlling it directly.

A final example would be managing slew/wrap limits and slew speeds,
which is a case again where primary decision-making control should be in
the telescope control system at the drives level. The scheduler can be
designed to consider estimated slew speeds as well as logic around
avoiding hitting wrap limits unnecessarily, and make decisions
accordingly, but it should not be responsible for directly controlling
the way that the drives respond to a given position request. Instead,
the scheduler will be responsible for generating a parameter set
including the requested position, which the telescope control system
will accept and slew to. We expect any low-level drive functions such as
unwrapping will similarly be automatically handled as part of monitoring
and control rather than on the scheduler side.

### Management of survey progress

At the lowest level, each attempted observation will be tracked in a
database that can be accessed via the command line. This database will
contain information about the specification parameters, variables
associated with the attempted observation (if it starts), logs of the
progress of the observation and other information as relevant. There
will also be a visual web-based interface to this database that is
designed to offer quick and comprehensive insight to what has been
observed (or attempted to be observed) on the array. This web-based
interface should be designed to be readily accessible to a wide range of
relevant human experts (including science PIs) who will need to have
oversight over survey progress and status; and should work on a range of
devices (e.g., laptops, tablets, phones) to ensure distributed oversight
of the survey progress is possible and straightforward. This visual
interface does not need to give control of the array (since that will be
primarily handled by the automated scheduler), but instead will allow
the relevant human experts to track and oversee what is happening.

Ideally, the web-based platform will offer other useful functionality as
required. One example would be to aid with transparency of the scheduler
decision-making process (for relevant staff) by showing logs, current
variables and states associated with the scheduler and potentially
offering ways for human experts to adjust or adapt the decision-making
process if needed. Another example would be for statistical and visual
assessment of the observations -- e.g., being able to view/calculate
success rate and efficiency over a given period for reporting, or
interactively view the portion of the sky covered for a given period. It
will be important in designing this platform that 1) relevant parties
likely to use it are consulted for possible use cases, and 2) that it is
designed in a way that allows it to be extended readily in future to
cover use cases that are inevitably missed at the time of initial
design.

### Simulation plans

The scheduler will be designed to have at least two simulation modes: 1)
when run manually by a human in "current status" simulation mode, it
will run through its logic processes and report on what it would choose
to do next given the current state of the system (either at the current
time or at an arbitrary time specified), and 2) it can be run in a
simulation mode with a specified set of initial conditions (and
probabilistic error rates or interruptions), an observing pool and a
time range and will report on what it would choose to do over that given
time period. These simulation modes will support the exploration and
investigation of the decision-making process employed by the scheduler
based on its existing logic, and also enable human experts to test and
analyze the impact of possible changes to that logic. In the absence of
the full automated scheduler, more basic and fundamental simulations
will be carried out in the lead-up to array construction that will
inform the future development of both the scheduler and the eventual
proper simulation modes.

## Human involvement in operations

The modern era is one where computing and automation have advanced
considerably, such that systems which traditionally involved high levels
of human oversight can be transitioned to ones requiring more specific
and targeted human input. Operations of complex systems such as
telescopes is one such example, where the data has become increasingly
multi-dimensional and of such large scale that it makes increasingly
less sense for human operators to sit at the centre of monitoring and
control.

In the case of DSA-2000, there are several elements which suggest the
necessity of low dependency on consistent human effort:

Remoteness: the system will be overseen at a distance, with minimal or
no staff on site to watch either the telescope or the environment
closely

Distributed team: staff involved in DSA-2000 operations will be
minimally split between several sites, including OVRO, Pasadena and
(potentially) near DSA-2000 itself

Survey focus: the goal of conducting surveys at high efficiency requires
reducing the number of places where human reactions or interventions can
create bottlenecks

Scale: with 2000 antennas and a complex backend associated with each of
them, the number of monitoring points relevant to decision making about
operations will be in the millions (at least)

Low-cost budget: the project is aiming to build an array of ambitious
scale while being cost-efficient in terms of budget, and this will
require minimizing the reliance on human resources

With the intention of thus maximizing the operational throughput while
minimizing the costs to the project, the use of designated human
operators in the traditional sense is not seen as a necessary part of
the operational workflow. What will be necessary is having appropriate
automated monitoring and control in place (potentially involving AI and
designed with a collaborative intelligence model in mind) such that the
relevant human expertise can be provided at points where it is
necessary.

It will likely be beneficial to have a designated operations team in
place, but with the right amount of automation alongside a small
fraction of distributed development/software support, this team can be
relatively small. As a minimal example, this team could consist of:

1.  Science operations lead (from specification to raw data production)

2.  Data operations lead (processing of the raw data)

3.  Archive operations (storing and transferring the processed data).

A fraction of operational support would be required from domain experts
in the relevant parts of the DSA-2000 system (e.g., covering support for
issues with antennas, receivers, digital backends, etc). This should be
allocated as part of the ongoing roles for those who have the relevant
expertise in these systems (e.g., at the 10-20% level, adjusted based on
what is required but ideally kept at a low consistent level).

It is noted that student involvement and training is expected to be part
of the overall commissioning and operations of DSA-2000, and this can be
factored into the plan for how the autonomous scheduler interacts with
relevant human experts. For example, students could be rostered on as
general contact points as part of standard operations (e.g., the first
point of contact if something urgent needs to be brought to attention)
and trained in both how the automated system works at a high level, as
well as how best to react if something is alerted to them. For this
model to work, there should be dedicated effort into designing this such
that the value both provided by the students and for the students is
maximised (to ensure engagement and investment in the role that they
would be acting in).

## Data Quality Assurance

The combination of multidimensional complexity, automation and real-time
workflows in DSA-2000 necessitates comprehensive and reliable data
quality assurance approaches. Specifically, it will be important to be
able to isolate issues and adjust the system quickly in the case of poor
quality to minimize the impact on recorded data, connecting monitoring
data from hardware, software, raw data and processed data. Many of the
subtleties of data quality for DSA-2000 will become most apparent during
the commissioning and early science phase, when the array is established
enough to produce data at a scale and of the quality expected during
full survey operations.

The planned approach for data quality is two-fold: 1) preventative data
quality assurance in the form of (mostly unsupervised) anomaly
detection, and 2) reactive data quality assurance that is based on lived
experience with the array as it evolves towards full survey operations.

### Preventative data quality assurance

This will primarily take the form of anomaly detection, using
unsupervised (or semi-unsupervised) machine learning on available data
-- both telescope monitoring data and data products. Based on experience
with similar telescope arrays (e.g., ASKAP, Apertif), we expect that raw
data autocorrelations will provide a useful insight into the state of
each antenna and enable identification of systematic issues affecting a
given antenna, subset of a given antenna, digital system (e.g.,
correlator) or environment. This form of anomaly/outlier detection can
be prepared early in the commissioning process and further developed
during commissioning but will be most effective when the array is able
to (mostly reliably) produce consistent data.

### Reactive data quality assurance

The reactive forms of data quality assurance will be developed as part
of the commissioning process, based on learnings from the telescope data
while it is handled and assessed closely. We expect this form of data
quality assurance to be largely driven by human insight and expertise,
making links between components of the system that more directly
identify issues or problems with the array (compared with the more
generic assessment to be provided by anomaly detection).

### Links with Collaborative Intelligence

Alongside trends of increasing machine learning and artificial
intelligence are parallel discussions about Collaborative Intelligence
(CINTEL), which specifically focus on the most effective ways that
humans and machines can collaborate with an emphasis on identifying the
unique areas where human expertise and insight is most valuable. This
topic will be highly relevant to DSA-2000 which - to efficiently survey
the sky - will need to be as automated as possible with high efficiency
and reliable data quality. As such, we expect an allocation within the
DSA-2000 team to be focused on designing, implementing and improving the
data quality assurance workflows such that the reliance on human
intervention or judgement is minimized while the data quality output is
maximized.

## Software and Service Management

Software is used to operate the telescope, the real-time processing, and
communicate its state to users. Services are persistent processes that
run software to facilitate communication between subsystems or between
automated and human actors. Since software is updated often and depends
on other software, we must carefully plan for its management and
continual updates.

### Software management

We will use the version control system git to track development
progress, associate performance to code changes and release code. Groups
may develop in the same software repository by creating branches for new
features. After unit testing and review, these changes are merged and
made available to other developers of the same repository.

The complexity of software and the number of distributed developers
motivates a continuous integration and testing system. We will use this
concept to prevent (or restrict) small errors in software from cascading
into systemwide failures. At the lowest level, we will use unit test
frameworks that are available in most software languages (e.g., "pytest"
for Python). New feature code should pass the most common style check
tool in their language (e.g., PEP8 for Python and gofmt for Go).
Automated linting of code should be encouraged by integrating it with
automated testing frameworks.

Code reviews will be performed to ensure consistency with style
requirements and minimal coding standards. Reviews will also ensure
changes are consistent with feature requests backed by requirements or
bug reports. The goal here is to control code creep and maintain a
consistent architecture and standards.

After features are unit tested and reviewed, they can be merged into the
main branch for integration testing with other software repositories.
This will happen in dedicated hardware that includes other software from
the same subsystem (e.g., monitor and control interfaces to the
post-processing system). Teams will have a fixed schedule for testing
the deployed software (e.g., every Wednesday). This builds confidence in
the live system and helps developers plan to deploy new features.
Deployable versions of all software packages should be uniquely tagged
both in source code repositories, as well as in all deployable
artifacts. A record of versions of all software packages deployed in
production will be maintained. Ideally, a versioned, complete software
bill of materials for every deployed package will be maintained as part
of the deployment record to support reproducibility.

Software issues and development will be managed with a ticketing or
issue management system. Tickets are assigned to define new features or
issues. These tickets can be grouped into milestones to develop new
capabilities. These milestones can drive planning through "agile",
"scrum", or other software development practices.

### Service management

Services are the software analog of a hardware component. They are
designed to be highly available resources that perform basic tasks.
Users of services may be either automated or human actors. An example of
a service is a tool that accumulates logs from software systems and
makes errors discoverable by operators.

As services are made of software, they must be tested as any software
component. Beyond testing, they need to be monitored and controlled,
just as hardware components are.

We will develop services based on experience with operations, both on
arrays built before DSA-2000 and the array itself. The commissioning
phase will refine the service requirements and iterate on their design.
As institutional knowledge grows, the operations will transition from
in-person or scripted operation of services to automated, discoverable,
monitored services.

The design of the services should support both manual and automated
operations from the beginning. This requires a hierarchy that separates
"low" concerns from "high" concerns. Automation is done by building
tools that have visibility and understanding of low concerns, but can
abstract them into high concerns. An example of this is a service to
determine the quality data coming from an antenna; there are many
complex inputs into this determination, but ultimately a service should
decide whether the antenna is good enough to use (yes or no).

## Data Management

"Data" can refer to the science products made by the telescope, metadata
that helps understand the state of the data (especially its value), and
configuration information that defines how the system should operate.
All these kinds of data need to be managed carefully to meet our goals
of providing scientific utility for most of the operational lifetime of
the DSA-2000.

### Radio Camera Processor data management

Data products created by the radio camera processor sub-system are
delivered in real time to the data management sub-system and are not
managed by the radio camera processor sub-system after their production.
These data products are written to files on one or more file systems
that are also available to the data management sub-system machines. The
qualities of these data products indicative of their availability
(*e.g.,* error correction, redundancy, failure modes) are solely a
function of the file systems on which the files are written.

### On-Site data management

The array will produce science quality data at a high rate that is
written to an on-site archive. This on-site archive will function as the
primary source of the bulk of the data generated by the array. An
on-site and off-site backup will be created at the same time and reflect
the same state of the on-site storage system. The off-site copy will be
physically delivered to a safe location (TBD) every four months.

The on-site data storage system will be backed up by a high-density
storage device (e.g., tape drives) and physically moved off site. The
goals of the backup are to allow restoration of the core science
products in the event of a major problem. Examples include (1) a major
disaster such as a fire or hacking of the control building and (2)
accidental deletion of significant data in the on-site archive. Securing
against these scenarios requires two copies be made: one stored on site
to allow relatively easy restoration of data and one stored off site for
maximum safety with less convenience.

### Off-Site data management

An all-sky mosaic of continuum image data will be sent to IPAC for
processing and serving to the public. We currently assume that the site
will have a fiber connection to a nearby town with high capacity to the
internet via a commercial service provider. Transfer from site to IPAC
must be done slowly, due to limitations on use of IPAC bandwidth. If
that limit is too slow, then disks can be shipped from site to IPAC on a
similar cadence as the off-site data backup.

At IPAC, the public archive will be shared via an architecture that is
compatible with both on-premises and cloud-based deployment, since the
economics and performance considerations may change over the lifetime of
the DSA-2000 project. The data services will be designed to be
compatible with both Posix-like filesystems and cloud-style object
stores as storage backends.

Multiple off-site archives will be supported and integrated with a
single DSA-2000 data portal managed by IPAC. This is done via
data-discovery and metadata services existing IVOA standards. Users at
one site may query for the existence of data at other sites and either
access it, perhaps in limited quantities, remotely, or navigate to the
archive interface and computing resources of the appropriate site.

### Configuration Management

Configuration management covers the hardware and software configuration
of the telescope. Hardware configuration management is supported by the
delivery of an Operational Support Baseline (OSBL), containing all the
design and as-built documentation. The OSBL will be maintained and
updated throughout the lifetime of the telescope.

The primary aim of software configuration management is always to manage
reproducible, deployed software configurations, although this goal can
be challenging given the methods and varieties of software configuration
in practice. All deployable software packages, as well as sets of
configuration parameters should be associated with version numbers to
facilitate configuration management. It is likely that software packages
and configuration parameter sets that are consistent with some subset of
package versions will be directly managed by staff during testing and
commissioning. Ideally the tools used by staff in testing and
commissioning will also be used to ensure that system-wide
configurations are reproducible and deployable with minimal effort by an
array operator, but this capability itself will require development
effort.

## Security 

Security is site dependent, and the preliminary provisions will be
adjusted as the confidence of permitting approval increases during the
Final Design Phase. There may be a need for security considerations as
there could be a concern about theft/vandalism. Provision has been made
for 24/7 security presence on-site. Access control will be in place for
buildings, including a dual layer access control for the data center.
Security can be augmented by cameras. The final security situation will
be evaluated with input from the local community and the Bureau of Land
Management; and presented at the Final Design Review, based on a
confirmed location.

### Cybersecurity 

The existing cybersecurity plan is found in the Project Execution Plan.
We are looking into bringing in consultants or support to help further
refine and implement the plan. This includes the NSF Cybersecurity
Center of Excellence, Trusted CI and have worked with various
observatories. https://www.trustedci.org/ or [Woodstar
Labs.](https://woodstarlabs.org/services/)

# Array Maintenance Concept 

Array availability requires that at any given point, at least 97% of the
antennas should be online and available for science use. It follows then
that no more than 60 antennas should be offline undergoing preventative
or reactive maintenance at any given time, but this would be the
worst-case scenario and it would of course be better if the
instantaneous number of antennas offline were significantly less than
that. From initial installation of an antenna, it will be incorporated
into the array until either 1) the antenna or a component fails, in
which case it will be taken offline for preventative maintenance, or 2)
it reaches the two-year maintenance threshold and then all components at
risk of failing are replaced. Hands-on maintenance will generally be
designed to be completed by teams of two people and will incorporate
usage of Utility Terrain Vehicles (UTV) to minimize the need for
dedicated new roads across the array, which would be additional
environmental disturbance. Unplanned hands-on maintenance will be
preceded by remote diagnostics, using sub-arrays. This creates the
requirement for sub-arrays, even though there is no science case for it.

### Installation and tracking of antennas

Each antenna and its components when installed will be tracked in an
accessible database, which will note the associated dates/ages and
maintenance records of each part of the antenna. This will be used to
track the age of components in the case of expiration dates for module
replacement as well as for tracking the history of repairs or faults
associated with each antenna.

### Determination of MTBF and MTTR

Mean time between failure (MTBF) and mean time to repair (MTTR) for
DSA-2000 antennas will be determined based on experience during
construction and prototyping as well as during commissioning, alongside
predictions based on antenna design. MTBF should not significantly
burden the requirement for antenna maintenance and MTTR should be
minimized. Other important elements to determine as part of the
commissioning phase will be the mean time it takes to travel to each
antenna safely (and how this varies depending on the location of the
antenna) as well as the mean time to service different potential
failures. As the array ramps up towards full survey operations, these
data will be in turn used to refine the scale of maintenance staff
required when DSA-2000 is nominally operational.

### Operational impact of antennas under maintenance

Given that a fraction of the array will be offline at any given point,
the operational systems will need to be designed to support and handle
this system state. This means that each antenna (or group of antennas)
will need to be able to be isolated from the system, e.g., put in a
local state, both soft local (via software) and hard local (e.g., at the
antenna, for safety). Reintegrating antennas on a regular basis will be
a standard part of operations, which means handling the calibration
state of antennas will be important. Recalibration and reintegration
into the array shall be supported by the relevant subsystems.
Reintegration processes can be scheduled to minimize impact on the
operational array.

The engineering and maintenance tasks, which will be on-going while the
array is operational, necessitates that the array is capable of
operating with sub-arrays, even if there is no scientific requirement
for it. Antennas taken out of the array can be operated individually or
in groups as a sub-array to enable testing and development. All
subsystems will need to be sub-array capable, or at least, sub-array
aware. Up to 4 sub-arrays could be operational at one time, given
multiple maintenance teams. Apart from the main array, the sub-arrays do
not require fully automated operation.

### ML/AI for planning and scheduling maintenance

As noted in [Section 2.3](#data-quality-assurance), the use of ML/AI
techniques will be adopted where suitable to ensure high data quality
and efficient throughput. We expect the maintenance database to
incorporate at least basic intelligence on this front to track the
history of antennas and identify when particular antennas are
approaching their maintenance windows. The degree to which AI might be
used to plan and schedule maintenance is an open opportunity, in the
sense that it should minimally be able to provide simple data on which
antennas need to be dealt with in the near term, but in the ideal case
could take into account e.g. antenna location, staff rosters, existing
scheduled maintenance and provide an optimized plan for carrying out the
maintenance itself. It would similarly be an optimal outcome if the
maintenance database were linked in a meaningful way to monitoring data,
such that identifying preventative maintenance paths could be a possible
option if desired (though it would depend on the cost-benefit of this
kind of approach, as it may be simpler to just reactively replace where
necessary or aim to reach the two-year window).

### Logistics support

The scale of the DSA-2000 is a large step up from traditional radio
astronomy instruments. Support must be streamlined in order not to cause
excessive operational cost. The system will be supported with a model
that draws from the military, with the following levels corresponding to
the O-I-D model:

1.  Organizational level (O-level): performed on-site, where the
    equipment is located, for example antenna scheduled maintenance.

2.  Intermediate level (I-level): performed on-site, but the equipment
    is taken to the Production and Maintenance building or Control
    building for maintenance in a workshop or laboratory.

3.  Depot level (D-level): performed off-site -- either at OVRO, or at a
    contractor facility.

With many parts, we will implement a comprehensive logistics support
plan. This includes the tracking of maintenance activities and spare
parts. An inventory management system will be deployed during the
beginning of the implementation phase and will first be used to track
pre-production test parts and then rolled out for all construction
materials at the Line Replaceable Unit (LRU) level. Ideally, the
inventory management system will use bar codes, or a similar radio
frequency interference (RFI) friendly mechanism, that can be easily
scanned, and updates tracked within the inventory management software.

#### Antenna Maintenance 

Antenna maintenance will form a large part of the O-level maintenance
load. The antennas are designed for minimum maintenance, including
automatic oiling of bearings. Monitor points are designed to identify as
many failure modes as possible, including temperatures of mechanical
components, drive currents, pointing behavior, solar power system
status, etc. These will be used to predict potential failure and allow
scheduling outside routine scheduled maintenance.

The most likely failures are currently judged to be the drive motors,
which are designed to be easily replaceable, both mechanically and
electrically. These and other potential failure components will have
defined procedures that will allow repair or replacement in less than a
day, including travel time to the antenna. Other mechanical or
electromechanical items include bearings, drive belts, encoders, and
limit switches. Signal path and monitor and control components will be
implemented as LRUs. All maintenance will be designed to not require any
equipment that produces RFI.

## Internal/External Communication and Troubleshooting 

The operations concept includes a distributed workforce with some staff
on site while others are at OVRO, Caltech, and elsewhere. We plan to
continue using Slack as the primary means of informal, logged,
transparent communication. The communication to site will be primarily
through Slack to maintain a log of communication. There will always be
at least one person within the main site buildings that is reachable and
able to communicate with the on-site observatory staff.

We plan to use Jira as the centralized issue tracker across the system,
particularly for any issues related to software, data products, or at
system-level. Tracking of hardware-only issues can be tracked within the
inventory management system.

The observatory will maintain a periodic telecon (bi-weekly to monthly)
and a monthly newsletter is recommended to keep the project's science
community informed. The goal of these is to ensure there is a way for
community members to raise any issues identified with the data and to
communicate the status of the observations.

## Antenna Access Plan 

An antenna access plan will be developed for the final site with the
assistance of Praxis Broadband Networks. The access plan will maximize
the use of existing roads and use the paths from the fiber optic cable
installation to reach each antenna to minimize environmental impact and
the creation and proliferation of roads. The paths will be marked using
GPS.

# Site Infrastructure Concept 

The overarching goal is to minimize infrastructure and environmental
impact of the site infrastructure. The location of the buildings is
planned to be near the highway midway through the North-South length of
the site to minimize the amount of new ground disturbance from the
buildings and minimize the amount of trenching needed for the fiber
optic network.

Depending on permitting conditions, we plan to truck in water and truck
out waste. To aim for net zero power, we will have a combination of grid
power and solar power for the buildings. Power can be procured from
renewable resources too.

Three buildings will be constructed -- a Control Building, including the
processing data center, a Maintenance and Fabrication Building, and an
Accommodation Building. All services will enter the array at the
location of the buildings. For our preferred site, we have identified a
location that will use already disturbed land, further minimizing
environmental impact.

## Array Infrastructure Concept 

The post of each antenna will be driven directly into the soil using a
vibratory hammer. This avoids the use of any concrete or cement for the
foundations. Each antenna will be connected by fiber optic cable and
powered by solar panels and batteries. The solar panels are planned to
be attached to a frame that sits on top of the ground. The fiber optic
network connecting the antennas will be plowed rather than trenched and
has been designed to minimize the amount of plowing required.

## Computer Infrastructure

Where feasible, a containerization framework will be utilized to
optimize compute resources. The microservice paradigm plays well with
container frameworks especially when the microservice is stateless.
Containers also provide software isolation which can include OS flavor
and tooling.

### Backups

All software and configuration will exist in Git repos in a cloud
service and are automatically backed up. Additional redundancy is
provided by the multitude of developers having clones of these
repositories on their individual computers.

On-site backups of monitor data and container snapshots can be
accomplished using opensource software. The depth of such backups will
be limited to hardware and storage costs.

## Site Buildings 

We will plan for three buildings:

1.  Building 1: The Control Building, which will host all on-site
    electronics. This building will also include a control room, office
    and meeting space, and laboratory facilities for intermediate level
    maintenance. The electronics will be hosted in a data center, with
    cooling and power management. The building will include
    electromagnetic shielding to prevent RFI reaching the array.

2.  Building 2: A maintenance and fabrication facility, used during
    construction as a store and antenna assembly workshop, then later
    during operations to house all the maintenance equipment and
    workshops.

3.  Building 3: Temporary/emergency accommodation for security
    personnel, staff, visiting scientists and students.

We have identified an old quarry, where we plan to locate the buildings.
This will provide additional RFI shielding from the terrain.

### Control Building (Building 1) 

The control building will be a building of \~10,000 sq. ft. with a
ground floor and a basement. The building will house the hardware for
part of the Analog Signal Path, the Radio Camera Frontend, Radio Camera
Processor, Pulsar Timing, Data Management, Monitoring and Control,
Timing and Synchronization, Observation Planner, as well as all central
networking hardware in a basement to help shield radio frequency
emission (RF). The building will require plumbing/water and HVAC system
capable of maintaining stable temperature for the computer hardware in
the basement. A fire suppression system for the data center that is both
human and equipment friendly will be installed. If the service entrance
is not on the same level as the data center, equipment handling will be
provided to transport racks and computers.

The ground floor will contain break room space for daily maintenance
workers, lab space to work on electronics, an electronics store for
spares, and a basic kitchen.

A rough outline of the building requirements is as follows:

-   Space, cooling and power for 100 racks of equipment

-   [1 MW]{.mark} power consumption

-   Power management systems (UPS)

-   Thermal management systems (HVAC or other means for temperature
    regulation as appropriate)

-   Fire suppression system

-   The data center will be constructed with a false floor for cool air
    distribution, and space for cable management and hot air extraction
    above.

The Control Building will form the hub for on-site activities. It will
also host the reception for visitors, although the site buildings are
not specifically intended to receive many visitors.

### Maintenance Building (Building 2) 

The maintenance will be a large, open building of \~10,000 sq ft. The
building can be partitioned appropriately for the project phase. The
building will be designed to house vehicles, store equipment, and
facilitate the integration and maintenance of antenna parts.

Given the climate at the preferred site, the building will include
heating.

### Accommodation Building (Building 3)

The Accommodation Building will provide accommodation for up to 12
people for any potential need for use of the facility overnight. This is
expected for security purposes, during commissioning and in case of
emergency situations that prevent short term exit from the site or
require staff to remain on site. Since all teams will consist of a
minimum of two people, 12 rooms will allow two teams across three daily
shifts to have accommodation at the same time. The technical support
staff are expected to commute daily from Ely and would not routinely use
the accommodation facilities.

## Vehicles and Fuel 

During operations, the array area will not have any new roads, instead,
access to antennas will be by access paths, planned to minimize
environmental impact. Enclosed UTVs will be used to perform tasks that
do not require a large load capacity. The UTVs are not roadworthy and
will only be used in the array. We are planning to procure 4 UTVs for
this purpose. Given the climate, the UTVs will be enclosed, with some
form of climate control. UTV's could be electric, or fuel powered -- the
choice will be based on practical considerations and cost.

For maintenance tasks that require a larger load capacity, as well as
transport of equipment to and from the site, 4 off-road capable site
trucks will also be purchased. One of these will be used to transport
fuel to site for other vehicles (including UTV's). The regular transport
of spares to and from OVRO will also use one of the site trucks.

We expect that customized vehicles with cranes will be used during
implementation to install the antennas on pedestals. In case an antenna
needs to be removed from the pedestal during operations, we will retain
one of these vehicles during operations.

## Power

The total system power is estimated to be [1MW]{.mark}. The bulk of the
power is consumed by the computing equipment in the Control Building,
which is sourced from the local grid, operated by Mount Wheeler Power
for the preferred site.

Mount Wheeler Power has an option to purchase renewable power at a
premium. This will be used judiciously to control the sustainability of
the telescope. In addition, we will opportunistically install solar
panels on the building roofs to reduce the reliance on grid power. This
is subject to the power system achieving the required RFI performance,
which will be analyzed prior to a decision.

A UPS system in the Control Building will allow graceful shutdown in
case of power failure. Since antennas have local solar power, the
antennas will automatically enter stow if communications with the
Monitoring and Control system is lost.

System startup will be phased to control inrush currents.

The antenna stations will each have a solar power station, with
photovoltaic solar panels, batteries, and charge controllers. It is
expected that the charge controllers will be custom designed to minimize
RFI. The antennas will run from the DC battery power directly, to reduce
the need for inverters that can cause additional RFI. The charge
controllers will be installed in shielded enclosures with ample
filtering of all cables to the panels and antenna.

Antenna station power will be optimized to control downtime due to power
outages, rather than to guarantee 100% uptime. A 1% loss due to power
availability is built into the system availability model.

Battery maintenance is designed not to perturb the 2-year antenna
station maintenance cycle.

## Water 

Availability of site water will determine whether water needs to be
trucked in, or well water can be used. This will be assessed during the
permitting process. Water use is estimated at 40,000 gallons per year,
based on experience with water use at CARMA and OVRO.

The baseline water supply, pending the requisite approvals, is from a
well with a suitable filtration system. The baseline treatment of sewage
is by a septic system. If either of these are not allowed, water will be
trucked in, and waste will be trucked out, adding suitable storage
systems.

Requirements for water used for wildfire suppression will be assessed in
consultation with the Bureau of Land Management and the local community.

## On-Site Communications 

The team will use VHF radios (tested and approved for RFI) for
communications to coordinate activities in the array area, and safety. A
repeater will be installed (if needed) to ensure good coverage across
the entire site. Vehicles will have radios, and hand-held units will be
available to staff who work in the array.

An emergency IP phone will be available inside electronics enclosures to
provide redundant means of communication.

All maintenance communications will be recorded as part of the
maintenance logs.

VoIP phones will be available in all buildings for regular or emergency
communications.

# RFI Monitoring

Due to the sensitivity and scale of the array, it will be important to
track and monitor the RFI environment as well as rapidly identify any
degrading changes to the RFI situation. This will be achieved in three
ways:

1.  Dedicated RFI environment monitoring with a monitor system sensitive
    enough to cover DSA-2000 requirements.

2.  Dedicated RFI surveys on a designated cadence with the DSA-2000
    system to capture the RFI environment as seen by the array, and
    potentially locate any RFI culprits.

3.  Analysis and monitoring of the DSA-2000 data itself via raw data and
    flags.

The RFI monitor system will consist of an antenna which covers the
DSA-2000 frequency range (and sufficiently beyond), which will
constantly scan and record data. This will give live insight into the
RFI situation across the band and provide historic data which can be
explored and analyzed via an archive. It is important that the monitor
be sensitive enough to represent the environment that DSA-2000 is also
sensitive to, although clearly it will be far from the same sensitivity
as the array itself.

On an appropriate cadence (e.g., every three months), RFI analysis of
the raw and processed data will be performed to compare against the
baseline and detect any new signals. This system should be automated as
much as possible and can exist as a semi-isolated package which plugs
into the relevant data flows. It is likely that ML/AI techniques will be
relevant here, particularly to identify new signals of significance that
may pose issues for data quality. In the case of new anomalous RFI
signals, the automated system will have avenues to flag/raise these with
relevant human experts who can assess the data and determine the
appropriate course of action.

# On-site safety 

A comprehensive Safety Plan will be developed for the site. Dedicated
safety staff will be identified and trained in at least:

1.  Safety Management

2.  First Aid

3.  Evacuation Management

4.  Fire Fighting

5.  Emergency coordination

In addition, in collaboration with BLM, dedicated plans may be developed
for:

-   Wildfire management and prevention

-   Flooding management and prevention

-   Earthquake response

-   Lightning protection

A site safety officer will be appointed, with alternates as required to
ensure there is always a site safety officer on site.

Response plans will also be developed in collaboration with the nearest
emergency services, to ensure mutual awareness of activities and
capabilities.

# Off-site Support Infrastructure Concept 

The nearest town to the preferred site is Ely, Nevada. Ely has a a small
but healthy tourism industry that the town is actively developing.
Accommodation in and around Ely should suffice for occasional use. The
local labor force will be preferentially recruited from the area to ease
the difficulty of relocations. More information on Ely is available at
several websites, including at <https://elynevada.net/>.

OVRO will serve as the depot level maintenance location, where the
operations engineering team will be located. It is envisaged that
engineers will periodically visit the site to support the on-site
maintenance team with challenging issues. These visits can also serve as
transport for spares to and from the site, although a dedicated weekly
transport service will also be instituted. OVRO will also host the Test
Array, which will serve as a staging platform during operations. All new
deployments, whether hardware or software, can be tested in a
representative environment at OVRO before deploying to site.

# Transition from Commissioning to Operations 

We plan for the array to undergo increasingly comprehensive phases of
testing in order to effectively transition to operational readiness.
Engineering completion will be verified by acceptance tests, first
performed per subsystem, followed by system level testing. These tests
will aim to prove that the telescope, or a feature of the telescope,
meets the engineering requirements. After acceptance tests are
successfully concluded, any new features or functions of the telescope
will go through a commissioning phase as part of being integrated into
the current state of the operational array.

It will be critical to adopt an approach of consistent integration and
testing during construction, in order to identify potential operational
challenges as early as possible and have time to adapt or adjust as
needed. To that end, we anticipate using early features of the
scheduler, monitoring/control and data processing (as well as other
relevant subsystems) as soon as possible, and we also aim to be
conducting ongoing observational tests with the growing subset of the
full array. During the lead-up to construction we will document the
expected verification mechanisms for science requirements as part of a
science verification plan, and use this to guide the overlapping
transition from construction to commissioning to operations. This
transition will not be seen as having hard borders giving the nature of
telescope construction, and instead we aim to keep many of the same
people involved in engineering, commissioning and operations across the
construction period (with varying fractional commitment as required).

We will aim to produce early science data as construction progresses,
using as much of the full operational workflow as possible, but we
expect these earlier data products to be less representative of the
final survey data. Where feasible we also intend to use the existing
OVRO-LWA and DSA-110 systems as commissioning test platforms for
compatible features across the system. Towards the end of construction,
we plan to conduct pilot surveys for condensed periods that are as close
to representative of the full survey operations mode as possible. We
expect the collaboration with the broader science community to be
similarly ramping up over the course of construction, with feedback on
data quality and science requirements being incorporated throughout the
whole process.

# Community Engagement Concept 

The public and the local community represent important stakeholders to
the project. The remote location and small towns in the area can be
substantially changed by the presence of a large project. It is our
intention to ensure that any changes are for the better of the
communities in the area. The project also holds the potential to create
jobs and inspire a new generation of radio astronomers, engineers and
technicians.

To support this, an Education and Public Outreach program will be
established. This program has two main goals:

1.  Train the next generation of STEM Workforce by creating education
    and training programs that prepare students for the jobs of
    tomorrow.

2.  Foster a science-informed society that appreciates astronomy and
    radio wave technology\'s impact on our daily lives and cosmic
    understanding.

More details are contained in the DSA-2000 EPO Design document, document
number D2k-00020-EPO-OTH.

In collaboration with the local community, the project will plan a
visitors center in a suitable off-site location. This could be in the
nearest town, or next to the nearest main road. Given the low cost of
the antennas, it will be possible to place a DSA-2000 antenna at the
visitors center.

# Requirements

The following table summarizes the requirements that result from the
Concept of Operations.

  --------------------------------------------------------------------------------------------
  **Reference**   **Requirement   **Requirement Text**    **Notes**      **Cross-reference**
                  Name**                                                 
  --------------- --------------- ----------------------- -------------- ---------------------
  COP-0001                                                               

  --------------------------------------------------------------------------------------------

# Acronyms

  -----------------------------------------------------------------------
  AI            Artificial Intelligence
  ------------- ---------------------------------------------------------
  BLM           Bureau for Land Management

  CARMA         Combined Array for Research in Millimeter-wave Astronomy

  CINTEL        Collaborative Intelligence

  D-level       Depot level (logistics support)

  DDT           Director's Discretionary Time

  DSA-110       The DSA-110 telescope at OVRO

  GPS           Global Positioning System

  HVAC          Heating. Ventilation and Air Conditioning

  I-level       Intermediate level (logistics support)

  IP            Internet Protocol

  IPAC          Infrared Processing & Analysis Center
                (https://www.ipac.caltech.edu/)

  IVOA          International Virtual Observatory Alliance

  LRU           Line Replaceable Unit

  ML            Machine Learning

  MTBF          Mean Time Between Failures

  MTTF          Mean Time to Failure

  MTTR          Mean Time to Repair

  O-level       Organizational level (logistics support)

  OS            Operating System

  OSBL          Operational Support Baseline

  OVRO          Owens Valley Radio Observatory

  OVRO-LWA      Owens Valley Radio Observatory -- Long Wavelength Array

  RF            Radio Frequency

  RFI           Radio Frequency Interference

  TBD           To be determined

  ToO           Target of Opportunity

  UPS           Uninterruptable Power Supply

  UTV           Utility Terrain Vehicle

  VHF           Very High Frequency
  -----------------------------------------------------------------------
