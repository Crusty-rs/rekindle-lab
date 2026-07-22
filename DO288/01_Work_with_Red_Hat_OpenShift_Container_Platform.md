# Red Hat OpenShift Container Platform (DO288) Exam Cheat Sheet

## OpenShift Objectives & Essential Commands

| Topic | What You Must Know | Key Commands |
|---|---|---|
| **Cluster Access & Navigation** | Understand OpenShift objects: projects, pods, services, routes, deployments. Know how to inspect API resources. | ```bash
oc login -u <user> -p <pass> <cluster-url>
oc whoami
oc api-resources
oc explain <resource>
``` |
| **Projects / Namespaces** | Projects isolate applications and resources. Always verify your active project before deploying. | ```bash
oc new-project <name>
oc project <name>
oc projects
oc status
``` |
| **Deploy Single Container Apps** | Create applications from images and expose them using services/routes. | ```bash
oc new-app <image>
oc get pods
oc expose svc/<service>
oc create route edge --service=<service>
``` |
| **Deploy Multi-Container Apps** | Understand that containers inside the same Pod share networking and storage. Use templates/manifests for multi-component apps. | ```bash
oc process -f <template.yaml> | oc create -f -
oc apply -f <file.yaml>
oc get pods -o wide
``` |
| **Health Probes (High Priority)** | Know the difference:<br><br>**Liveness:** Restarts unhealthy containers.<br>**Readiness:** Removes containers from traffic until ready. | ```bash
oc set probe dc/<app> \
--readiness \
--get-url=http://:8080/health

oc set probe dc/<app> --remove
``` |
| **Basic Git Operations** | Know how OpenShift uses Git repositories for builds. Be comfortable with branches, commits, and pushes. | ```bash
git clone <repo>
git checkout -b <branch>
git add .
git commit -m "message"
git push
``` |
| **Source-to-Image (S2I)** | Core DO288 concept. OpenShift combines source code + builder image to create container images automatically. | ```bash
oc new-app <builder-image>~<git-url>

oc start-build <buildconfig> --follow

oc logs bc/<name>
``` |
| **ImageStreams & Internal Registry** | ImageStreams track container images and trigger deployments when images change. | ```bash
oc get imagestreams

oc tag <source-image> \
<project>/<image>:<tag>

oc import-image <image>
``` |
| **Private Registry Authentication** | Create registry secrets when pulling images from secured registries. | ```bash
oc create secret docker-registry <secret-name> \
--docker-server=<registry> \
--docker-username=<user> \
--docker-password=<password>

oc secrets link builder <secret-name>
``` |
| **Web Console Usage** | Know Developer Perspective features: Topology, Logs, Events, Builds, Metrics. | UI Tasks:<br>• Open Topology<br>• View Pods<br>• Check Logs<br>• Inspect Events<br>• Monitor Metrics |

---

# Exam Must-Know Concepts

## Deployment Flow

