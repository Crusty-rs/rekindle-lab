# Red Hat OpenShift Container Platform Objectives Cheat Sheet

| Objective | What You Should Know | Common Tasks / Commands | Workplace Usage |
|---|---|---|---|
| Work with Red Hat OpenShift Container Platform | Understand OpenShift architecture, projects, nodes, pods, services, routes, deployments, and operators | `oc login`, `oc get`, `oc describe`, `oc explain` | Connect to clusters, check resources, troubleshoot applications |
| Create and work with multiple OpenShift projects | Understand projects as isolated environments for teams and applications | Create projects, switch projects, view resources inside projects | Manage dev, test, and production environments separately |
| Create and deploy single-container applications | Deploy applications from images or source code | Create deployments, expose services, create routes | Deploy web applications running in containers |
| Create and deploy multi-container applications | Understand applications made of multiple containers working together | Manage pods with multiple containers, deployments, services, environment variables, storage | Run applications with frontend, backend, database, or sidecar containers |
| Use application health monitoring | Understand readiness probes, liveness probes, startup probes, and application status | Check pod health, events, logs, probes | Detect failures and allow OpenShift to restart unhealthy containers |
| Understand basic Git usage | Know basic Git workflow and how OpenShift uses source repositories | `git clone`, `git add`, `git commit`, `git push`, branches | Manage application source code used for deployments |
| Work with Git in OpenShift deployments | Understand source-to-image (S2I), build configurations, and Git-based deployments | Connect Git repositories, create builds, trigger deployments | Automatically build and deploy applications from code changes |
| Configure OpenShift internal registry | Understand OpenShift image registry and image management | Push, pull, tag, and manage images inside the cluster | Store and manage container images securely inside OpenShift |
| Configure registry requirements | Understand storage, authentication, access control, and image policies | Configure registry settings and permissions | Ensure images are available and controlled correctly |
| Manage applications using the web console | Use OpenShift Console for daily administration | Create applications, view workloads, inspect logs, edit resources | Perform common administration tasks without CLI |
