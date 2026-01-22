Devops and SRE

devops is to address challenges in treaditional software dev
- promotes collalborative culture
- workflow, automation, and tools to support it

workflow: enable collab between developers and operators

automation streamlines software development and delivery, reduce human assistance, and facilitate feedback between devs and ops

CI: continuous integration
CD: continuous delivery
CI/CD speeds up dev and delivery
- things like github actions
- automated tests
automates everything after code changes to the deployment

### Continuous Integration
the process of automatically and frequently integrating code changes into a shared repo

detects integration issues early, commits trigger an automatic workflow that builds and tests the system after the commit.

### Continuous Delivery
When a code change passes the testing, it gets pushed to a staging environment. more testing is run in staging (integration, load testing, regression testing) which only passes with **manual** trigger to push to prod.

#### Continuous Deployment
same process as delivery, but everything doesn't require manual triggers. less concerned about bugs and more focus on speed. as soon as the program passes tests in staging, it will be deployed to prod.

---

### Tool support
in a java project, this includes
- gradle for builds
- junit for testing
- jenkins for CI process
- docker for deployment
- k8s for operation
- jira for planning
- git for source tracking
- datadog for monitoring

these tools automate each of these steps and make the lives of devs easier

### Containerization
basically barebones vms. a process that virtualizaes resources for software applications.

packages everything you need into a container that runs the same across platforms and devices. no more local dependencies.

flexible, secure, and promotes collaboration since everyone runs the same.

resource intensive though.

since containers are isolated from the host system, it prevents malware from accesing our local files and keeps our system safe.

--- 

## SRE

practice of automating IT operations.

focus on response time and software reliability.
automates incident response, prod system management, performance monitoring, and reporting

benefits:
- metric reporting
- clarify and evaluate customer expectations
- productivity
- detect issue before they reach users

broken down into 3 components:

1. Service Level Agreement
2. Service Level Objective
3. Service Level Indicator

**SR engineers build SLI to drive SLO to use SLA**
