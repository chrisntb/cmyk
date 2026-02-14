# Architecture

## Software

### Kubernetes (K8s)

K8s is written in Go and we may need to extend K8s `https://kubernetes.io/docs/concepts/extend-kubernetes/` so it makes sense to also use Go for the management services.
In addition the K8s Go client `https://github.com/kubernetes/kubernetes/releases` is always released first, often by several months.

We need web and CLI interfaces and we would like users to be able to create their own interfaces.
We also want it to be easy to switch frontend technologies since they change often.
These requirements mean we will take an API first approach.
We will implement the web interface as a single page web app (SPA) in order to 'keep us honest' with respect to the API first approach.

### Slurm

TODO

## Infrastructure

Infrastructure will be K8s and Slurm based.
The management services (APIs, database), and web interface will be located in a K8s management cluster, separate from the HPC clusters.

TODO

## Technical Design

A user will submit a job using a management API which will perform checks and then use the K8s/Slurm APIs to schedule the job.

### K8s

The job will be allocated to a K8s queue (`Kueue`) and scheduled to run as a `pod` on an appropriate HPC `node`.
It is technically possible to do some logic in K8s itself but this is not recommended, see `https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/#should-i-add-a-custom-resource-to-my-kubernetes-cluster`.

A user will be able to track the process of their job from submission, through to running and completion.
A user will be able and download their job results.

TODO

## Functional Design

Key attributes:

- Job
  - CPU
  - Memory
  - GPU
  - Hardware constraints
  - Duration
- User
- Group
- Tenant

Relationships

- A group is part of a tenant
- A user is part of zero or more tenants

TODO
