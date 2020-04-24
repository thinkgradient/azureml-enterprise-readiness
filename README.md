<p align="center">
    <img width="500" height="300" src="Azure-ML-Icon.png">
</p>

# Azure Machine Learning Service 

Created by: 
* Fatos Ismali, Data Solutions Architect, Databricks 
* Joe Plumb, Data Solutions Architect, Microsoft
* Muffajul Ali, Data Solutions Architect, Microsoft
* Lorea Arrizabalaga, Data Solutions Architect, Microsoft
* Adelina Balasa, Data Solutions Architect, Microsoft

# Table of Contents

- [Introduction](#Introduction)
- [Scalable Azure ML Deployments: Guidelines for Networking, Security, and Capacity Planning](#scalable-ADB-Deployments-Guidelines-for-Networking-Security-and-Capacity-Planning)
  * [Azure ML 101](#Azure-Databricks-101)
  * [Map Workspaces to Business Units](#Map-Workspaces-to-Business-Divisions)
  * [Deploy Workspaces in Multiple Subscriptions to Honor Azure Capacity Limits](#Deploy-Workspaces-in-Multiple-Subscriptions-to-Honor-Azure-Capacity-Limits)
    + [Azure ML Workspace Limits](#ADB-Workspace-Limits)
    + [Azure Subscription Limits](#Azure-Subscription-Limits)
  * [Consider using Key Vault for Authentication to AML during Traning and Inferencing](#Consider-Isolating-Each-Workspace-in-its-own-VNet)
- [Networking](#Deploying-Applications-on-ADB-Guidelines-for-Selecting-Sizing-and-Optimizing-Clusters-Performance)
  * [Isolate Compute and Storage in their own VNET within the same Subscription](#Select-the-Largest-Vnet-CIDR)
  * [Use Compute Instances behind VNET for Exploratory Data Analysis](#Do-not-Store-any-Production-Data-in-Default-DBFS-Folders)
- [Monitoring](#Deploying-Applications-on-ADB-Guidelines-for-Selecting-Sizing-and-Optimizing-Clusters-Performance)
  * [Monitor and manage an AKS cluster for deployment of models](#Always-Hide-Secrets-in-a-Key-Vault)
  * [Use AppInsights for monitoring scoring requests](#Always-Hide-Secrets-in-a-Key-Vault)
- [Automation](#Deploying-Applications-on-ADB-Guidelines-for-Selecting-Sizing-and-Optimizing-Clusters-Performance)
  * [REST APIs](#support-interactive-analytics-using-shared-high-concurrency-clusters)
   * [CLI](#support-batch-etl-workloads-with-single-user-ephemeral-standard-clusters)
   * [ARM Templates](#favor-cluster-scoped-init-scripts-over-global-and-named-scripts)
- [Authentication and Authorization](#Running-ADB-Applications-Smoothly-Guidelines-on-Observability-and-Monitoring)
  * [RBAC](#Collect-resource-utilization-metrics-across-Azure-Databricks-cluster-in-a-Log-Analytics-workspace)
   + [Roles](#Querying-VM-metrics-in-log-analytics-once-you-have-started-the-collection-using-the-above-document)
- [Cost Management](#Running-ADB-Applications-Smoothly-Guidelines-on-Observability-and-Monitoring)
- [Appendix A](#Appendix-A)

