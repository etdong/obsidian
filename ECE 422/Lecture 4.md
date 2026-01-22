**Continuing with SRE**

### Review
CI/CD: main automation for devops stuff. continuous integration, continuous delivery and continuous deployment.

**Quiz**
CI pipeline fails frequently due to flaky tests. eventually, devs begin to ignore failures because:
**C** High false positive rate.

What is the key requirement for implementing continuous delivery?
**C** Automated testing and integration pipelines.

What is the main difference between continuous delivery and deployment?
**B** Continuous deployment automates deployment to prod, whereas delivery requires manual approval.

### SRE
to recap, it's the IT side automation.

it provides comprehensive metric reporting which allows for data-driven decisions. 
monitoring the system with these metrics can detect anomalies before they become issues. 
allows for easier definition of customer requirements and tangible objectives.

these metrics are called **SLI's**: service level indicators.

service level agreement is the contract. the service level objectives are the goals to achieve from the promises made in the agreement. service level indicators are the metrics to check and meet the goals.

**SLA**
service level agreements are between the business team and the customer.

SLA is a legal binding document that includes:
- service scope and description
- performance metrics
- responsibilities
	- whether it be for the SRE team or the client
- support and maintenance
- penalties

SLA will improve trust with customers and promote communication and clarify expectations.

e.g.
IT service SLA terms:
- service availability: 99.9% uptime for servers.
- resolution time: minor issues will be resolved within 10 hours.
- penalties: if uptime falls below 99%, client receives a 10% service credit for the affected month.

SLI vs. KPI
KPI demonstrates how effectively a company is at achieving their goals.
- sales revenue
- web traffic

SLA is for service expectations, KPI is for performance

**SLO**
measurable goals defined in the SLA that out lines a performance level for an aspect of the service.

SRE team is involved in this step in cooperation with the dev team to provide insight into whether the SLOs are realistic.

the product manager defines the customer-perspective SLOs

dev team will ensure the code meets the SLOs

e.g.
SLA: 99.9% Canvas uptime
	SLO: 99.9% uptime for the site on weekdays

basically more specific and measurable objectives.

**SLI**
the metric that measures the performance and availability of a service. SLO compliance is based on these metrics.

### Availability and Reliability
availability is percentage of operational time.
usually expressed in number of nines.

one nine: 90 percent, 36 days of downtime
etc

MTBF: mean time between failure
MTTR: mean time to repair

availability = MTBF / (MTBF+MTTR)


reliability is the likelihood of a system to perform it's function without failure.

R(t) = e^(-t/MTBF)

### Error budget
how much downtime a system can afford without upsetting customers.

teams "spend" error budget by making unreliable changes, eating into the budget with errors.

depending on the error budget spend, we move around the team structure.

more error budget means we can afford to have more devs and applying more changes. otherwise, we need more ops to increase reliability.

### Best practices
- use non-technical language in SLAs
- fewer SLOs as possible
- build an error budget
- shoot lower and provide higher
- don't provide every metric as an SLO

### How to improve these -abilities?
reduce frequency of faults
- upgrade system
- continuously improving software
	- reactive

design systems that are fault tolerant. failures will **always** happen, just design the systems to work even when failures occur.

### Fault tolerance

e.g. PDF reader crashes, but restarts itself after sending error report.

failures in safety-critical systems can be catastrophic, fault tolerance is prioritized in these systems.

no software should ever be assumed to be fault-free.
but there are two faults to try to avoid:
- building the product wrong
- building the wrong product
	- remember the objectives and requirements

fault tolerant systems consist of:
- error detection,
- diagnosis
- confinement
- and recovery
## Overview
SRE focuses on reliability, devops focus on delivery

SRE is to devops what scrum is to Agile. one implementation of a philosophy and principles, but not a subset. they are not competing methods.
