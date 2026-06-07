ExternalDNS Helm Chart Changelog
All notable changes to this project will be documented in this file.

The format is based on Keep a Changelog, and this project adheres to Semantic Versioning.

UNRELEASED
Add value .service.enabled to enable the creation of the Kubernetes service.
Fixed
RBAC compliance checkbox for dnsendpoints/status #6442 @vflaux
v1.21.1
Added
Add value .sourceNamespace to watch a namespace which is different from the one that external-dns is installed into when .namespaced is true. (#6297) @jplitza
Add option to enable Gateway API ListenerSet support. (#6381) @speer
Add support for bool in extraArgs. (#6179) @farodin91
Add value .namespaceOverride to render chart resources into a namespace different from the release namespace, for subchart installs that want their own namespace. (#6389) @alliasgher
Changed
Update ExternalDNS OCI image version to v0.21.0. (#6354) @vflaux
Fixed
Avoid creating cluster-scoped RBAC for Gateway API sources when running namespaced with gatewayNamespace set. Namespace listing permissions are now only added when gatewayNamespace is unset. (#5843) @TobyTheHutt
Ensure container arguments are passed in as strings (#6264) @KhooHaoYit
Ensure container arguments are passed in as strings when extraArgs is a map (#6284) @vflaux
v1.20.0
Added
Add option to set annotationPrefix (#5889) @lexfrei
Changed
Grant networking.k8s.io/ingresses and gateway.solo.io/gateways permissions when using gloo-proxy source. (#5909) @cucxabong
Update ExternalDNS OCI image version to v0.20.0. (#6005) @vflaux
Fixed
Fixed the missing schema for .provider.webhook.serviceMonitor configs (#5932) @chrisbsmith
Fixed incorrect indentation of selector labels under spec.template.spec.topologySpreadConstraints when topologySpreadConstraints is set. (#6054) @andylim0221
v1.19.0 - 2025-09-08
Added
Add option to configure annotationFilter via dedicated chart value. (#5737) @dshatokhin
Changed
Grant discovery.k8s.io/endpointslices permission only when using service source. (#5746) @vflaux
Update ExternalDNS OCI image version to v0.19.0. (#5819) @stevehipwell
v1.18.0 - 2025-07-14
Changed
Update RBAC for Service source to support EndpointSlices. (#5493) @vflaux
Update ExternalDNS OCI image version to v0.18.0. (#5633) @elafarge
Fixed
Fixed the lack of schema support for create-only dns policy in helm values (#5627) @coltonhughes
Fixed the type of .extraContainers from object to list (array). (#5564) @svengreb
v1.17.0 - 2025-06-04
Changed
Allow extraArgs to also be a map enabling overrides of individual values. (#5293) @frittentheke
Update CRD. (#5287) @mloiseleur
Update CRD. (#5446) @mloiseleur
Update ExternalDNS OCI image version to v0.17.0. (#5479) @stevehipwell
Fixed
Fix wrong type definitions for webhook probes. (#5297) @semnell
Update schema with latest plugin release. (#5510) _@mloiseleur
v1.16.1 - 2025-04-10
Changed
Set defaults for automountServiceAccountToken and serviceAccount.automountServiceAccountToken to true in Helm chart values. (#5207) @t3mi
Fixed
Correctly handle txtPrefix and txtSuffix arguments when both are provided. (#5250) @ivankatliarchuk
Add missing types in the schema for empty values. (#5228) @ivankatliarchuk
Add missing types in the schema for empty values. (#5207) @t3mi
v1.16.0 - 2025-03-20
Added
Add helm testing framework helm plugin unittest. (#5137) @ivankatliarchuk
Add ability to generate schema with helm plugin schema. (#5075) @ivankatliarchuk
Add docs/contributing/dev-guide.md#helm-values guide. (#5075) @ivankatliarchuk
Changed
Regenerate JSON schema with `helm-values-schema-json' plugin. (#5075) @ivankatliarchuk
Update ExternalDNS OCI image version to v0.16.1. (#5201) @stevehipwell
v1.15.2 - 2025-02-14
Changed
Added transportservers resource to ClusterRole when specifying f5-transportserver or f5-virtualserver as a source. (#5066) @visokoo
Fixed
Fixed handling of non-string types in serviceAccount.metadata.annotations field. (#5067) @hjoshi123
Fixed regression where affinity.nodeAffinity was being ignored. (#5046) @mkhpalm
v1.15.1 - 2025-01-27
Added
Added ability to configure imagePullSecrets via helm global value. (#4667) @jkroepke
Added options to configure labelFilter and managedRecordTypes via dedicated helm values. (#4849) @abaguas
Changed
Allow templating serviceaccount.annotations keys and values, by rendering them using the tpl built-in function. (#4958) @fcrespofastly
Updated ExternalDNS OCI image version to v0.15.1. (#5028) @stevehipwell
Fixed
Fixed automatic addition of pod selector labels to affinity and topologySpreadConstraints if not defined. (#4666) @pvickery-ParamountCommerce
Fixed missing Ingress permissions when using Istio sources. (#4845) @joekhoobyar
v1.15.0 - 2024-09-11
Changed
Updated ExternalDNS OCI image version to v0.15.0. (#4735) @stevehipwell
Fixed
Fixed provider.webhook.resources behavior to correctly leverage resource limits. (#4560) @crutonjohn
Fixed provider.webhook.imagePullPolicy behavior to correctly leverage pull policy. (#4643) @kimsondrup
Fixed to add correct webhook metric port to Service and ServiceMonitor. (#4643) @kimsondrup
Fixed to no longer require the unauthenticated webhook provider port to be exposed for health probes. (#4691) @kimsondrup & @hatrx
v1.14.5 - 2024-06-10
Added
Added support for extraContainers argument. (#4432) @omerap12
Added support for setting excludeDomains argument. (#4380) @bford-evs
Changed
Updated ExternalDNS OCI image version to v0.14.2. (#4541) @stevehipwell
Updated DNSEndpoint CRD. (#4541) @stevehipwell
Changed the implementation for revisionHistoryLimit to be more generic. (#4541) @stevehipwell
Fixed
Fixed the ServiceMonitor job name to correctly use the instance label. (#4541) @stevehipwell
v1.14.4 - 2024-04-05
Added
Added support for setting dnsConfig. (#4265) @davhdavh
Added support for DNSEndpoint CRD. (#4322) @onedr0p
Changed
Updated ExternalDNS OCI image version to v0.14.1. (#4357) @stevehipwell
v1.14.3 - 2024-01-26
Fixed
Fixed args for webhook deployment. (#4202) @webwurst
Fixed support for gateway-grpcroute, gateway-tlsroute, gateway-tcproute & gateway-udproute. (#4205) @orenlevi111
Fixed incorrect implementation for setting the automountServiceAccountToken. (#4208) @stevehipwell
v1.14.2 - 2024-01-22
Fixed
Restore template support in .Values.provider and .Values.provider.name
v1.14.1 - 2024-01-12
Fixed
Fixed webhook install failure: "http-webhook-metrics": must be no more than 15 characters. (#4173) @gabe565
v1.14.0 - 2024-01-10
Added
Added the option to explicitly enable or disable service account token automounting. (#3983) @gilles-gosuin
Added the option to configure revisionHistoryLimit on the K8s Deployment resource. (#4008) @arnisoph
Added support for webhook providers, as a sidecar. (#4032 @mloiseleur
Added the option to configure ipFamilyPolicy and ipFamilies of external-dns Service. (#4153) @dongjiang1989
Changed
Avoid unnecessary pod restart on each helm chart version. (#4103) @jkroepke
Updated ExternalDNS OCI image version to v0.14.0. (#4073) @appkins
Deprecated
The secretConfiguration value has been deprecated in favour of creating secrets external to the Helm chart and configuring their use via the extraVolumes & extraVolumeMounts values. (#4161) @stevehipwell
v1.13.1 - 2023-09-08
Added
Added RBAC for Traefik to ClusterRole. (#3325) @ThomasK33
Added support for init containers. (#3325) @calvinbui
Changed
Disallowed privilege escalation in container security context and set the seccomp profile type to RuntimeDefault. (#3689) @nrvnrvn
Updated ExternalDNS OCI image version to v0.13.6. (#3917) @stevehipwell
Removed
Removed RBAC rule for already removed contour-ingressroute source. (#3764) @johngmyers
v1.13.0 - 2023-03-30
All Changes
Updated ExternalDNS version to v0.13.5. (#3661) @GMartinez-Sisti
Adding missing gateway-httproute cluster role permission. (#3541) @nicon89
v1.12.2 - 2023-03-30
All Changes
Added support for ServiceMonitor relabelling. (#3366) @jkroepke
Updated chart icon path. (#3492) kundan2707
Added RBAC for Gateway-API resources to ClusterRole. (#3499) @michaelvl
Added RBAC for F5 VirtualServer to ClusterRole. (#3503) @mikejoh
Added support for running ExternalDNS with namespaced scope. (#3403) @jkroepke
Updated ExternalDNS version to v0.13.4. (#3516) @stevehipwell
v1.12.1 - 2023-02-06
All Changes
Updated ExternalDNS version to v0.13.2. (#3371) @stevehipwell
Added secretConfiguration.subPath to mount specific files from secret as a sub-path. (#3227) @jkroepke
Changed to use registry.k8s.io instead of k8s.gcr.io. (#3261) @johngmyers
v1.12.0 - 2022-11-29
All Changes
Added ability to provide ExternalDNS with secret configuration via secretConfiguration. (#3144) @jkroepke
Added the ability to template provider & extraArgs. (#3144) @jkroepke
Added the ability to customise the service account labels. (#3145) @jkroepke
Updated ExternalDNS version to v0.13.1. (#3197) @stevehipwell
v1.11.0 - 2022-08-10
Added
Added support to configure dnsPolicy on the Helm chart deployment. @michelzanini
Added ability to customise the deployment strategy. mac-chaffee
Changed
Updated ExternalDNS version to v0.12.2. @stevehipwell
Changed default deployment strategy to Recreate. mac-chaffee
v1.10.1 - 2022-07-11
Fixed
Fixed incorrect addition of namespace to ClusterRole & ClusterRoleBinding. @stevehipwell
v1.10.0 - 2022-07-08
Added
Added commonLabels value to allow the addition of labels to all resources. @stevehipwell
Added support for Process Namespace Sharing via the shareProcessNamespace value. (#2715) @wolffberg
Changed
Update ExternalDNS version to v0.12.0. @vojtechmares
Set resource namespaces to {{ .Release.Namespace }} in the templates instead of waiting until apply time for inference. @stevehipwell
Fixed rbac.additionalPermissions default value.(#2796) @tamalsaha
v1.9.0 - 2022-04-19
Changed
Update ExternalDNS version to v0.11.0. (#2690) @stevehipwell
v1.8.0 - 2022-04-13
Added
Add annotations to Deployment. (#2477) @beastob
Changed
Fix RBAC for istio-virtualservice source when istio-gateway isn't also added. (#2564) @mcwarman
