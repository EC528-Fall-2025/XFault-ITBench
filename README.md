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

[Sprint Demo 5](https://drive.google.com/file/d/1AbznDp1_FZbeADkSS-u9m7fgLYsWzg-W/view?usp=sharing) | [Sprint 5 Slides](https://docs.google.com/presentation/d/1vDy-XkxpKxu7oQufHX70eKDPdils_yKM1XO1QcuUlAY/edit?usp=sharing)

[Sprint 6 Final Demo](https://drive.google.com/file/d/1PdVGVk0_yyx3HCtBGq_pI5dv2XqUiou2/view?usp=sharing) | [Sprint 6 Slides](https://docs.google.com/presentation/d/1RhcIQhdgD88JB2Z0goD5vEzOQGQPzvb78vC7MwB2j24/edit?usp=sharing) | [Live Demo](https://drive.google.com/file/d/1YX5oM8A3yXoygniqeW23t_rfwpNY-9WJ/view?usp=sharing)

## Important Links 
The link to the main repository we are working on is [ITBench-Scenarios](https://github.com/itbench-hub/ITBench-Scenarios), which is apart of [ITBench's hub](https://github.com/itbench-hub) and the main point of fault scenario developments. Due to this project being open source, we have made branches on the main repository or forked the repository for version control. 

| Name | Fault Contribution Summary |
| --- | --- |
| [Tyler Nguyen, Forked Repo](https://github.com/tylrnguyen/ITBench-Scenarios) | <ul><li>Expired TLS Certificate Fault</li><li>Misconfigured Service Mesh Faults:<ul><li>Explicit Traffic Deny</li><li>Sidecar Proxy Disabling</li></ul></li></ul> |
| [Phyliss Darko, Forked Repo](https://github.com/phylisscity/ITBench-Scenarios) |  <ul><li>Fill Database Storage Fault</li> <li>Misconfigured DNS Fault</li> <li>Pod Anti-Affinity Preventing Scheduling</li><li>Pod Priority-Based Eviction Cascade</li><li>PodDisruptionBudget Blocking Node Drain</li></ul> |
| [Pree Simphliphan, Forked Repo](https://github.com/preespp/ITBench-Scenarios) | <ul><li>Node Resource Exhaustion</li> <li>Init-Container Hang</li> <li>Readiness Probe Flapping</li>|
| Ryan Malone (Our Past Member) | <ul><li>Istio Service Mesh (New Tools)</li></ul>|
| Vincent Candela (Our Past Member) | <ul><li>Database Resource Limit Fault</li></ul>|


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

Minimum Viable Product (MVP):
- Implement and extend 9 fault scenarios at least 3 fault scenarios per level

Extended goal:
- Implement and extend another 6 fault scenarios across each level
- New Tools introduced to ITBench such as Istio Service Mesh
  
**Out of Scope Features (Not included in this project)**:

- Creation of new AI agents (evaluation only)
- Support for non-kubernetes environments (testing assumes kubernetes as base) such as Python Unit Testing API
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

The architecture diagram now highlights the technologies in use for MVP: Prometheus (metrics), Jaeger (traces), OpenSearch (logs), and Kubernetes (fault orchestration). These integrations ensure each fault is observable and measurable by the AI agent.

This project extends ITBench’s fault injection and detection framework. The existing open-source framework involved Kubernetes. The new real-world fault scenarios will be studied and introduced to the framework with three levels of distributed systems:

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

Each fault scenario will be implemented and observed by monitoring tools such as Prometheus, Jaeger, OpenSearch, and Clickhouse, to be a metric of AI agents’ evaluation. Moreover, these mechanisms will be modular to be reused, combined, extended, and published into ITBench’s open-source framework.

#### Design Implications and Discussion
  - Modularity: Each fault mechanism should be pluggable for reusability and expansion in future use cases, such as security incidents, compliance failures.
  - Realism: Fault mechanisms must mimic real-world production incidents at major cloud providers and IBM SaaS incidents.
  - Observability: Faults will integrate with monitoring tools so that AI agents and SREs can detect traces, logs, or metrics for evaluation.

## Glossary

- SRE (Site Reliability Engineering)
A discipline focused on building and operating reliable, scalable systems using automation, monitoring, and fault tolerance.

- MCP (Model Context Protocol)
An open protocol that allows AI agents to securely access tools, APIs, logs, metrics, and contextual system data. ITBench uses MCP to enable agents to interact with observability systems like Prometheus, Jaeger, and OpenSearch.

- PDB (Pod Disruption Budget)
A Kubernetes mechanism that limits how many pods of an application can be voluntarily disrupted at once (e.g., during upgrades or maintenance), helping ensure service availability.

- OpenTelemetry (OTel)
A vendor-neutral observability standard for generating, collecting, and exporting metrics, logs, and traces. ITBench uses OTel-compatible data for benchmarking AI agents.

- FinOps
A practice that manages cloud financial operations, helping organizations control cloud costs and track resource efficiency.

- CISO (Chief Information Security Officer)
A senior executive responsible for an organization’s cybersecurity strategy and incident response readiness.

- Sidecar
A companion container in a Kubernetes pod that provides auxiliary functionality (e.g., logging, proxies, monitoring agents). Some faults involve sidecar misbehavior or failure.

- Eviction Cascade
A chain-reaction failure where Kubernetes evicts multiple pods due to resource pressure (CPU, memory, disk, or node-level stress), potentially causing widespread service disruptions.

## Acceptance criteria 

We will consider this project to be a success if the following concepts are established:

Overall Goal: Site Reliability Engineering (SRE) via creation of faults. 

Three Big General Goals

1. New fault mechanisms for SRE grounded in real-world incidents
    - Diagnose features and mitigate outages in production systems
      - Simulating system failures
      - Validating pipelines and incident response workflows 
      - Assessing how agents respond to complex fault conditions before deployment
2. Improved documentation / consumability
    - Enhance onboarding materials, examples, and fault scenario coverage
    - Ensure usability of ITBench for SRE-focused workflows and agentic software testing.
3. Add Istio Service Mesh tools for expanding fault scenarios based on this tool

Below are a rough listing of fault scenarios that we want to cover. Work will be completed to develop faults that sufficiently cover each use case. We may decide that certain faults will not be covered and (or) other use cases of faults should be added.

1. Application Level Mechanisms
    - Malformed data injections/database access methods: Fill Database Storage and Database Resource Limit
    - Misconfigured DNS (Network Policy) misconfigurations
2. Pod-Level Scenarios
    - Exhaust Node Resource
    - Hanging Init Container
    - Misconfigured Readiness Probe Flapping
    - Disabled Sidecar Proxy
    - Pod Anti-Affinity Preventing Scheduling
    - Pod Priority-Based Eviction Cascade
    - PDB Blocking Node Drain
3. Multi-service Faults
    - Expired TLS Certificate
    - Authorization Policy Deny

## Release Planning

Sprints

| # | Dates | Sprint Title | Focus / Deliverables |
| :------: | :------: | :------: | :------: |
| 1 | Sep 15 – Oct 1 | Foundations + Setup | Gain hands-on experience with Kubernetes, microservices, and OpenTelemetry |
| 2 | Oct 2 – Oct 15 | ITBench Familiarization + Istio Service Mesh Tools | Deploy ITBench in a Kubernetes cluster (Remote Cluster), implement Istio Service Mesh, explore existing fault injection mechanisms, and extend them by combining faults into new scenarios |
| 3 | Oct 16 – Oct 29 | Faults (Part 1) | Implement new fault mechanisms, including Database Resource Limit, Fill database storage fault, Misconfigured Service Mesh Fault, Exhaust Node Resources Fault, and expired TLS certificates fault|
| 4 | Oct 30 – Nov 12 | Faults (Part 2) | Revised Pull Request from Sprint 2 and continue to extend faults: DNS Misconfiguration Fault, Hanging Init Container Fault, Disabled Sidecar Proxies Fault, and Explicit Traffic Denial |
| 5 | Nov 13 – Nov 24 | Faults (Part 3) + Python Unit Testing | Research on Python Testing API for non-kubernetes users and implement new fault scenarios, including PodDisruptionBudget, Pod Priority-Based Eviction Cascade, Pod Anti-Affinity, and Misconfigured Readiness Probe Flapping |
| 6 | Nov 25 – Dec 8 | Wrap Up Pull Requests | Finish up all Pull Requests, Merged all branches to main branch for application-level, multi-service coordination and container/pod-level failures and Revise documentation | 

## Summary

We delivered an extension to ITBench that introduces a suite of new SRE-focused fault scenarios, complete with observability integrations, incident ground truth files, and cleanup workflows. All faults are reproducible on Kubernetes and validated end-to-end using Prometheus, Jaeger, Grafana, and ITBench’s scenario engine.

This project has showcased running multiple representative incidents, such as readiness flapping, network traffic misconfiguration, or pod-level fault scenarios, and demonstrated how AI agents can diagnose them using the added observability hooks and fault metadata.

## Installation Guide
- This installation guide is referenced from main repository written by our mentors and ITBench Team. Full instruction can be accessed via [this link](https://github.com/itbench-hub/ITBench-Scenarios/tree/main/sre)
- First step: clone ITBench GitHub Repo
```bash
git clone https://github.com/itbench-hub/ITBench-Scenarios
```

### Recommended Software

#### MacOS

- [Homebrew](https://brew.sh/)

### Required Software

- [Python3](https://www.python.org/downloads/) (v3.13.Z)
- [Helm](https://helm.sh/docs/intro/install/) (v3.16+)
- [Kubectl](https://kubernetes.io/docs/tasks/tools/)
- [OpenShift CLI](https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html/cli_tools/openshift-cli-oc) (Required Only for OpenShift)
- [awscli](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) (v2) (Required for Remote Cluster User)
- [kOps](https://kops.sigs.k8s.io/getting_started/install/) (Required for Remote Cluster User)

#### Installing Required Software via Homebrew (for MacOS)

1. Install [Homebrew](https://brew.sh/)
2. Install required software
```bash
brew install helm@3
brew install kubectl
brew install python@3.13
brew install openshift-cli
```

**Note (11/19/2025):** When installing from Brew, it symlinks to most recent version automatically. In the case of Helm, please follow the instructions provided to ensure that the right version responds to the `helm` command. Helm 4 is [currently not supported by the `kubernetes.core` Ansible module](https://github.com/ansible-collections/kubernetes.core/issues/1038) and thus cannot be used by ITBench until a newer version with compatability with it is provided.

#### Installing Required Software (for Red Hat Enterprise Linux -- RHEL)

1. Install Helm 3 by following the instructions [here](https://helm.sh/docs/v3/intro/install#from-script)
2. Set up kubectl by following the instructions [here](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/#install-using-native-package-management)
3. Set up Python by running:
```bash
sudo dnf install python3.13
```
4. Install the OpenShift CLI by following the instructions [here](https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html/cli_tools/openshift-cli-oc#cli-installing-cli_cli-developer-commands)

#### Deploying an Incident Scenario

##### Installing Dependencies (for initial setup only)
1. Navigate to sre directory
```bash
cd sre
```

2. Create a Python virtual environment
```bash
python3.13 -m venv venv
source venv/bin/activate
```

3. Install Python dependencies
```bash
python -m pip install -r requirements.txt
python -m pip install -r requirements-dev.txt
```

4. Install Ansible collections.
```bash
ansible-galaxy install -r requirements.yaml --force
```

5. Create the relevant environment variable files by running
```bash
make group_vars
```

#### Cluster Setup

##### Local Cluster

- Change directory to dev/local_cluster
```bash
cd dev/local_cluster
```

For instruction on how to create a kind cluster on MacOS, please see the instructions [here](https://github.com/itbench-hub/ITBench-Scenarios/blob/main/sre/dev/local_cluster/README.md).
For instruction on how to create a kind cluster on Red Hat Enterprise Linux (RHEL) virtual machine (VM) or bare-metal instance, please see the instructions [here](https://github.com/itbench-hub/ITBench-Scenarios/blob/main/sre/dev/local_cluster/README_RHEL.md).

##### Remote Cluster (Recommended)

_Note: The following setup guide has been verified and tested on MacOS, Ubuntu, and Fedora using the perscribed details._

_Note: For full instruction on original ITBench repository, please follow the link [here]([./dev/remote_cluster/README.md](https://github.com/itbench-hub/ITBench-Scenarios/blob/main/sre/dev/remote_cluster/README.md))._

_Note: Currently, only AWS is supported. AWS clusters are provisioned using [kOps](https://kops.sigs.k8s.io/)._

- Change directory to dev/remote_cluster
```bash
cd dev/remote_cluster
```

###### Installing Required Software via Homebrew (for MacOS)

1. Install required software
```bash
brew install awscli
brew install kops
```

###### Installing Required Software (for Red Hat Enterprise Linux -- RHEL)

1. Install the AWS CLI v2, curl, and jq by running:
```bash
sudo dnf install awscli
sudo dnf install curl
sudo dnf install jq
```
2. Set up kops by following the instructions [here](https://kops.sigs.k8s.io/getting_started/install/#linux)


###### 0. First Time Setup

Create the group variables for the development host. The `kops_cluster.yaml` file contains the configuration needed to customize the kops deployment.
```bash
make group_vars
```

The following variables are to be set in `group_vars/development/kops_cluster.yaml`
```
cluster:
  s3:
    bucket_name: "" # Bucket to which kOps will post cluster configurations in; bucket will be created if it does not exist
  ssh:
    public_key_path: "" # Public SSH key to be placed on the cluster nodes allowing for the nodes to be SSHed into; must be set if clusters are to be created.
```
_Note: A guide to creating SSH keys can be found [here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)._

Set up AWS credentials by running the following command. Enter the AWS access key ID and security access key when requested.
```bash
aws configure
```

###### 1. Create a new Kubernetes cluster using EC2 resources. Skip this step if you already have a cluster running.

The cluster configuration is defined in `group_vars/development/kops_cluster.yaml`.

```bash
make create_kops_cluster
```

###### 2. Export the cluster's kubeconfig to access the remote Kubernetes cluster:

```bash
make export_kops_kubeconfig
```

To export a cluster other than the one defined in `group_vars/development/kops_cluster.yaml`, get the full name of the cluster by running the following command:

```bash
make list_kops_clusters
```

Then, run the following command with the CLUSTER_NAME argument:

```bash
CLUSTER_NAME=<full name of cluster> make export_kops_kubeconfig
```

###### 3. Verify Cluster Access to test your connection to the cluster:

```bash
export KUBECONFIG=/tmp/<cluster_name>.yaml
kubectl get pods --all-namespaces
```

**Example:**
```bash
export KUBECONFIG="/tmp/development-m5.xlarge-aws.k8s.local.yaml"
kubectl get pods --all-namespaces
```

###### 4. Update the `kubeconfig` path in your global configuration:

```bash
vim ../../group_vars/environment/cluster.yaml
```

Set the absolute path where the kubeconfig should be downloaded:
```yaml
kubeconfig: "/absolute/path/to/kubeconfig.yaml"
```

**Example:**
```yaml
kubeconfig: "/tmp/development-m5-xlarge-aws.k8s.local.yaml"
```

###### 5. The cluster has been set up. Now let's head back to sre directory to deploy the incidents.
```bash
cd ../..
```

#### Running Incident Scenarios - Quick Start
- Change incident number based on the incident you would like to test INCIDENT_NUMBER= ....

##### 1. Start the Incident Scenario
Run the following command to deploy observability tools, monitoring stack, chaos engineering tools, application stack, and inject the fault for scenario 1:

```bash
INCIDENT_NUMBER=1 make start_incident
```

##### 2. Set Up Port Forwarding and Access Dashboards
Enable access to the Prometheus:

```bash
kubectl port-forward svc/prometheus-kube-prometheus-prometheus -n prometheus 9090:9090
```

Navigate to the following URLs in your browser:
```bash
# View alerts and metrics
http://localhost:9090/alerts
```

Enable access to the Jaeger Query UI:

```bash
kubectl port-forward svc/jaeger-query -n jaeger 8080:16686
```

Navigate to the following URLs in your browser:
```bash
# View traces
http://localhost:8080
```

_Note: instruction for this step is different from the original repository because there has been an update on ingress-nginx tool and it's not available for ITBench anymore._

If you are on a remote cluster, to display the ip endpoints, use the following commands 

```bash
export KUBECONFIG=/tmp/development-aws.k8s.local.yaml
```

```bash
kubectl -n kube-gateways get gateway
```

After copying the address displayed, append /prometheus/query and /jaeger to the address to view respective dashboards.

##### 3. Monitor Alert States
The system includes alerts that monitor:
- Deployment status across namespaces
- Service latency metrics
- Error rates across services

**Alert Behavior:**
- Default state: `Inactive`
- After a few minutes: `Firing` (indicating fault manifestation)

##### 4. Cleanup and Delete the Cluster 
When finished, undeploy by running:

```bash
INCIDENT_NUMBER=1 make stop_incident
```

Delete the Cluster (for Remote Cluster User)
To delete the cluster, run the following command:

```bash
make destroy_kops_cluster
```

To delete a cluster other than the one defined in `group_vars/development/kops_cluster.yaml`, get the full name of the cluster by running the following command:

```bash
make list_kops_clusters
```

Then, run the following command with the CLUSTER_NAME argument:

```bash
CLUSTER_NAME=<full name of cluster> make destroy_kops_cluster
```

See the [Original Developer Guide](https://github.com/itbench-hub/ITBench-Scenarios/blob/main/sre/DEVELOPER_GUIDE.md) for a step-by-step breakdown of the `make start_incident` process.
