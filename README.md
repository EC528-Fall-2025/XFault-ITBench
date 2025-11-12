# Extending Fault Mechanisms within ITBench

## Collaborators

| Name | Role | Email |
|---|---|---|
| Rohan Arora | Mentor | rohan.arora@ibm.com |
| Gerard Vanloo | Mentor | gerard.vanloo@ibm.com |
| Phyliss Darko | Developer | phylissd@bu.edu |
| Pree Simphliphan | Developer | prees26@bu.edu |
| Tyler Nguyen | Developer | tnguyen0@bu.edu |

## Sprint Demos

[Sprint Demo 1](https://drive.google.com/file/d/1Q8h8t-LOxZ-m1zKE-fySNAeK1Hii9WqP/view?usp=sharing) | [Sprint 1 Slides ](https://docs.google.com/presentation/d/1sjAw02g-9Nfv2HuaapXCvgmP0mxJ3uUInUmbL2SpxG8/edit?usp=sharing)

[Sprint Demo 2](https://drive.google.com/file/d/1spLHJLEG582y-zielfJ89qYbxFPkFPnP/view?usp=sharing) | [Sprint 2 Slides](https://docs.google.com/presentation/d/1BQi8PwxHS5iw87HWU4xMmLudjDrvHVy-P6j5rilcQBA/edit?usp=sharing) 

[Sprint Demo 3](https://drive.google.com/file/d/13YP4X5HrrwfF_hoi5Ezd54TD5P120mxO/view?usp=sharing) | [Sprint 3 Slides](https://docs.google.com/presentation/d/1romlamLLVoEkvpWZDKsn_MGA5TE14dJ_KxZlCQB0JlQ/edit?usp=sharing)

[Sprint Demo 4](https://drive.google.com/file/d/1uiP9xDFWdcezhT76KB4gGH28O60bI7Xr/view?usp=sharing) | [Sprint 4 Slides](https://docs.google.com/presentation/d/1RJDlipCBvV4zHnoD7KY9pYRlW9jpOT9y4Lcj1sIrGQc/edit?usp=sharing)


## Important Links 
The link to the main repository we are working on is [ITBench-Scenarios](https://github.com/itbench-hub/ITBench-Scenarios), which is apart of [ITBench's hub](https://github.com/itbench-hub) and the main point of fault scenario developments. Due to this project being open source, we have made branches on the main repository or forked the repository for version control. 

| Name | Fault Contribution Summary |
| --- | --- |
| [Tyler Nguyen, Forked Repo](https://github.com/tylrnguyen/ITBench-Scenarios) | <ul><li>Expired TLS Certificate Fault</li><li>Misconfigured Service Mesh Faults:<ul><li>Explicit Traffic Deny</li><li>Sidecar Proxy Disabling</li></ul></li></ul> |
| [Phyliss Darko, Forked Repo](https://github.com/phylisscity/ITBench-Scenarios) |  <ul><li>Fill Database Storage Fault</li> <li>Misconfigured DNS Fault |
| [Pree Simphliphan, Forked Repo](https://github.com/preespp/ITBench-Scenarios) | <ul><li>Node Resource Exhaustion</li> <li>Init-Container Hang</li> <li>Readiness Probe Flapping</li>|



## Vision and Goals of the Project

### Background

ITBench, started in early 2025, allows users to invoke replicable real-world scenarios in a sandbox environment to benchmark AI agents on their ability to detect, diagnose, and remediate failures regarding IT operations. The tool was created for IT professionals and researchers in fields such as Site Reliability Engineering (SRE), Information Security Operations (CISO), and Financial Operations (FinOps), where realistic simulation testing is essential for high-stakes operations. ITBench is still in its early stages of adoption and requires an expanded scope of fault injections (controlled and deliberate forced error for testing) and incidents (benchmark task built from fault injections) to ensure user confidence in an agent’s ability to automate IT operations. Current gaps include limited coverage in faults related to application-level services, multi-service coordination, and container/pod-level failures.

### Goal

Our goal as a team is to address gaps in ITBench by extending these fault injection mechanisms, particularly in the SRE space, broadening the realism and range of the tool’s benchmarking. The final vision of the project is to enable ITBench to simulate real-world incidents modeled after outages that have occurred at major cloud providers. Specifically, we want to expand the benchmarking with the following:
- Application-level faults: database/network connectivity, authentication. 
- Multi-service coordination: cross-service dependency compatibility, traffic/load management, cascading failures across services.
- Container/pod-level faults: resource management and lifecycle failures.

Secondary contributions may also include designing more incidents, enhancements through integration with relevant applications, and increasing general usability for end users.

## Users/Personas of the Project

The principal users of the extended ITBench fault mechanism are professionals and researchers who directly rely on realistic fault simulation to ensure the reliability of distributed systems and the effectiveness of AI-driven automation. Site Reliability Engineers are the primary focus of this project. They work under immense pressure to diagnose failures, mitigate outages, and maintain system reliability in complex production environments. ITBench provides them with a safe, controlled environment to:

- Simulate realistic system failures inspired by real-world cloud incidents.
- Validate pipelines and fault-tolerance mechanisms before deploying to production.
- Assess how AI-driven automation agents respond under cascading and multifaceted fault conditions.
- Train and refine operational playbooks for rapid incident detection, diagnosis, and mitigation.

By extending ITBench’s fault mechanisms, this project directly supports SREs in enhancing reliability engineering practices, ensuring resilience at scale, and strengthening confidence in AI-assisted operations.

#### Other Beneficiaries

While the main emphasis is on SRE use cases this semester, ITBench also provides equal value to:
- **Information Security Operations (CISO teams)**: Simulating authentication failures, compliance breaches, and governance-related fault conditions.


- **FinOps practitioners**: Analyzing the financial impact of cascading outages, failover inefficiencies, and automation strategies on cost-performance trade-offs.


## Scope and Features of the Project

The scope of this project is to extend ITBench’s fault injection and detection framework with realistic production-inspired failures that directly support Site Reliability Engineers (SREs) in testing, diagnosing, and improving system resilience. While CISO and FinOPs use cases remain relevant, the primary emphasis is on scenarios that reflect day-to-day reliability challenges SREs face in cooud-native environments. 

**In-Scope Features**:
- **Application-level Faults** - database connection errors, authentication/login failures, memory leaks, network policy configuration, and malformed data injection.
- **Container/Pod Level Faults** - pod evictions from resource pressure, volume mount and init container issues, node affinity misconfigurations, readiness probe failures, etc.
- **Multi-Service Coordination Faults** - load balancer misrouting, cascading cross-service failures, misconfigured mesh policies, and downstream rate-limiting or throttling. These represent the most severe reliability incidents, where dependencies multiply the impact of a single failure.
- **Observability** - integration of new fault scenarios with Prometheus, Jaeger, openSearch, etc, to support monitoring and tracing tools so that agent performance can be measured consistently. Also to ensure SREs have the metrics, traces,and logs necessary for root cause analysis and incidents triage.
- **Usability Enhancements** - creation of modular, reusable fault components and documentation updates so SREs and open source contributors can easily reproduce incidents, create new combinations, and test AI-driven remediation strategies.
  
**Out of Scope Features**:

- Creation of new AI agents (evaluation only)
- Support for non-kubernetes environments (testing assumes kubernetes as base)
- Major redesign of ITBench’s architecture (extending existing mechanisms, not rebuilding framework)

By setting these boundaries, the project ensures focus on realistic reliability scenarios. The result is a powerful testbed where SREs can validate whether AI agents respond as effectively as human engineers to production-scale failures; from small misconfigurations to multi-service outages.

## Solution Concept

### Global Achitectural Structure of the Project

<p align="center">
  <img src="https://github.com/user-attachments/assets/733391a6-7671-4b80-8e13-94bfc7ed1044" width="649" height="251" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/e610e024-2f8e-4a72-bb2c-dc9ffc6385c7" width="254" height="325" />
</p>



This project extends ITBench’s fault injection and detection framework. The existing open-source framework involved Kubernetes. The new real-world fault scenarios will be introduced to the framework with three levels of distributed systems:

#### 1. Application-Level Faults:
  - Database connection issues
  - Authentication or login failures from new services
  - Memory Leaks
  - Network policy misconfigurations
  - Malformed data injection
#### 2. Multi-Service Coordination Faults:
  - Load balancer failures
  - Cascading cross-service dependency fault mechanisms
  - Misconfiguration of the service mesh configuration
  - Rate-limiter on one of the downstream components
#### 3. Container/Pod-Level Faults:
  - Pod evictions (resource limit configurations, node, scheduling conflicts)
  - Volume mount issues
  - Init container failures
  - Node affinity misconfiguration
  - Readiness (liveness) probe failures
  - ImagePullBackoff due to registry unavailability

Each fault scenario will be implemented and observed by monitoring tools such as Prometheus, Jaeger, OpenSearch, and Clickhouse, to be a metric of AI agents’ evaluation. Moreover, these mechanisms will be modular to be reused, combined, extended, and published into ITBench’s open-source framework.

#### Design Implications and Discussion
  - Modularity: Each fault mechanism should be pluggable for reusability and expansion in future use cases, such as security incidents, compliance failures.
  - Realism: Fault mechanisms must mimic real-world production incidents at major cloud providers and IBM SaaS incidents.
  - Observability: Faults will integrate with monitoring tools so that AI agents and SREs can detect traces, logs, or metrics for evaluation.

## Acceptance criteria 

We will consider this project to be a success if the following concepts are established:

Overall Goal: Site Reliability Engineering (SRE) via creation of faults. 

Three Big General Goals

1. New fault mechanisms for SRE grounded in real-world incidents
    - Diagnose features and mitigate outages in production systems
      - Simulating system failures
      - Validating pipelines and incident response workflows 
      - Assessing how agents respond to complex fault conditions before deployment
2. Extending the mode of interaction(s) for agents via MCP
    - Enable broader more flexible agent interactions within ITBench. 
    - Provide agents with structure data access
      - logs, traces, error metrics, etc. 
3. Improved documentation / consumability
    - Enhance onboarding materials, examples, and fault scenario coverage
    - Ensure usability of ITBench for SRE-focused workflows and agentic software testing. 

Below are a rough listing of fault scenarios that we want to cover. Work will be completed to develop faults that sufficiently cover each use case. We may decide that certain faults will not be covered and (or) other use cases of faults should be added.

1. Application Level Mechanisms (Part I)
    - Network policy misconfigurations
    - Malformed data injections/database access methods
2. Application Level Mechanisms (Part II)
    - Authentication Errors and Bugs
    - Memory Leaks
3. Pod-Level Scenarios
    - Pod Evictions
    - Node Affinity Conflicts and Scheduling Failures
    - Readiness Probe Failures
    - Registry Unavailability Errors
4. Multi-service Faults
    - Multiservice Coordination Failures
    - Misconfigured Service Mesh Policies
    - Load Balancer Failures
    - Cascading Failures Across Services
    - Downstream Rate Limiting or Throttling/Race Conditions

## Release Planning

Sprints

| # | Dates | Sprint Title | Focus / Deliverables |
| :------: | :------: | :------: | :------: |
| 1 | Sep 15 – Oct 1 | Foundations | Gain hands-on experience with Kubernetes, microservices, and OpenTelemetry |
| 2 | Oct 2 – Oct 15 | ITBench Familiarization | Deploy ITBench in a Kubernetes cluster, explore existing fault injection mechanisms, and extend them by combining faults into new scenarios |
| 3 | Oct 16 – Oct 29 | Application-Level Faults (Part 1) | Implement application-level mechanisms, which will include faults triggered by network policy misconfigurations, and faults triggered by malformed data injection |
| 4 | Oct 30 – Nov 12 | Application-Level Faults (Part 2) | Continue to extend application-level faults, which this sprint will cover adding a new microservice with login/authentication to simulate authentication failures and introducing memory leak scenarios |
| 5 | Nov 13 – Nov 24 | Container/Pod-Level Faults | Implement pod-level scenarios, including pod evictions, node affinity conflicts leading to scheduling failures, readiness probe failures, and ImagePullBackoff errors due to registry unavailability |
| 6 | Nov 25 – Dec 8 | Multi-Service Faults | Implement multi-service coordination failures, including misconfigured service mesh policies, load balancer failures, cascading failures across services, and downstream rate-limiting/throttling scenarios | 
