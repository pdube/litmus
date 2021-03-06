<img alt="LitmusChaos" src="https://landscape.cncf.io/logos/litmus.svg" width="200" align="left">

# Cloud-Native Chaos Engineering; Kubernetes-Native Chaos Engineering; Chaos Engineering for Kubernetes

[![Build Status](https://travis-ci.org/litmuschaos/litmus.svg?branch=master)](https://travis-ci.org/litmuschaos/litmus)
[![Docker Pulls](https://img.shields.io/docker/pulls/openebs/ansible-runner.svg)](https://hub.docker.com/r/openebs/ansible-runner)
[![GitHub stars](https://img.shields.io/github/stars/litmuschaos/litmus?style=social)](https://github.com/litmuschaos/litmus/stargazers)
[![GitHub issues](https://img.shields.io/github/issues/litmuschaos/litmus)](https://github.com/litmuschaos/litmus/issues)
[![Twitter Follow](https://img.shields.io/twitter/follow/litmuschaos?style=social)](https://twitter.com/LitmusChaos)
[![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/3202/badge)](https://bestpractices.coreinfrastructure.org/projects/3202)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=litmuschaos_litmus&metric=alert_status)](https://sonarcloud.io/dashboard?id=litmuschaos_litmus)
[![BCH compliance](https://bettercodehub.com/edge/badge/litmuschaos/litmus?branch=master)](https://bettercodehub.com/)
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Flitmuschaos%2Flitmus.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2Flitmuschaos%2Flitmus?ref=badge_shield)
<br><br><br><br>


## Overview
Litmus is a toolset to do cloud-native chaos engineering. Litmus provides tools to orchestrate chaos on Kubernetes to help SREs find weaknesses in their deployments. SREs use Litmus to run chaos experiments initially in the staging environment and eventually in production to find bugs, vulnerabilities. Fixing the weaknesses leads to increased resilience of the system. 

Litmus takes a cloud-native approach to create, manage and monitor chaos. Chaos is orchestrated using the following Kubernetes Custom Resource Definitions (**CRDs**):
- **ChaosEngine**: A resource to link a Kubernetes application or Kubernetes node to a ChaosExperiment. ChaosEngine is watched by Litmus' Chaos-Operator which then invokes Chaos-Experiments 
- **ChaosExperiment**: A resource to group the configuration parameters of a chaos experiment. ChaosExperiment CRs are created by the operator when experiments are invoked by ChaosEngine. 
- **ChaosResult**: A resource to hold the results of a chaos-experiment. The Chaos-exporter reads the results and exports the metrics into a configured Prometheus server.

Chaos experiments are hosted on <a href="https://hub.litmuschaos.io" target="_blank">hub.litmuschaos.io</a>. It is a central hub where the application developers or vendors share their chaos experiments so that their users can use them to increase the resilience of the applications in production.


## Use cases

- **For Developers**: To run chaos experiments during application development as an extension of unit testing or integration testing.
- **For CI pipeline builders**: To run chaos as a pipeline stage to find bugs when the application is subjected to fail paths in a pipeline.
- **For SREs**: To plan and schedule chaos experiments into the application and/or surrounding infrastructure. This practice identifies the weaknesses in the system and increases resilience.


## Demo 
[![asciicast](https://asciinema.org/a/MOPQfmzA5NxgBs8DkMGROXpQw.svg)](https://asciinema.org/a/MOPQfmzA5NxgBs8DkMGROXpQw)


## Getting Started with Litmus
See <a href="https://docs.litmuschaos.io/docs/next/getstarted.html" target="_blank">Litmus Docs</a>.


## Contributing to Chaos Hub
See <a href="https://github.com/litmuschaos/community-charts/blob/master/CONTRIBUTING.md" target="_blank">Contributing to chaos hub</a>

## Adopters
See <a href="https://github.com/litmuschaos/litmus/blob/master/ADOPTERS.md" target="_blank">Adopters of LitmusChaos</a>


(*Send a PR to the above page if you are using Litmus in your chaos engineering practice*)

## Things to Consider
Some of the considerations that need to be made with Litmus (as a chaos framework), are broadly listed here. Many of these are already being worked on 
as mentioned in the [ROADMAP](./ROADMAP.md). For details or limitations around specific experiments, refer to the respective [experiments docs](https://docs.litmuschaos.io/docs/pod-delete/).

- Network chaos for container runtimes other than Docker, such as containerd, CRIO is not supported yet
- Litmus chaos operator and the chaos experiments run as kubernetes resources in the cluster. In case of airgapped environments, the chaos custom resources 
  and images need to be hosted on premise.
- When attempting to execute platform specific chaos experiments (like those on AWS, GCP cloud) the access details are passed via kubernetes secrets. Support
  for other modes of secret management with Litmus is yet to be tested/implemented. 
- Some chaos experiments make use of the docker api from within the experiment pods, and thereby require the docker socket to be mounted. User discretion is 
  advised when allowing developers/devops admins/SREs access for running these experiments.
- In (rare) cases where chaos experiments make use of privileged containers, the recommended security policies will be documented.

## License
Litmus is licensed under the Apache License, Version 2.0. See [LICENSE](./LICENSE) for the full license text. Some of the projects used by the Litmus project may be governed by a different license, please refer to its specific license.


[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Flitmuschaos%2Flitmus.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2Flitmuschaos%2Flitmus?ref=badge_large)

## Community notes
https://hackmd.io/a4Zu_sH4TZGeih-xCimi3Q


## Important Links
<a href="https://docs.litmuschaos.io">
  Litmus Docs <img src="https://avatars0.githubusercontent.com/u/49853472?s=200&v=4" alt="Litmus Docs" height="15">
</a>
<br>
<a href="https://landscape.cncf.io/selected=litmus">
  CNCF Landscape <img src="https://landscape.cncf.io/images/left-logo.svg" alt="Litmus on CNCF Landscape" height="15">
</a>
