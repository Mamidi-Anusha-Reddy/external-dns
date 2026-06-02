Values
Key	Type	Default	Description
affinity	object	{}	Affinity settings for Pod scheduling. If an explicit label selector is not provided for pod affinity or pod anti-affinity one will be created from the pod selector labels.
annotationFilter	string	nil	Filter resources queried for endpoints by annotation selector.
annotationPrefix	string	nil	Annotation prefix for external-dns annotations (useful for split horizon DNS with multiple instances).
automountServiceAccountToken	bool	true	Set this to false to opt out of API credential automounting for the Pod.
commonLabels	object	{}	Labels to add to all chart resources.
deploymentAnnotations	object	{}	Annotations to add to the Deployment.
deploymentStrategy	object	{"type":"Recreate"}	Deployment Strategy.
dnsConfig	object	nil	DNS config for the pod, if not set the default will be used.
dnsPolicy	string	nil	DNS policy for the pod, if not set the default will be used.
domainFilters	list	[]	Limit possible target zones by domain suffixes.
enableGatewayListenerSets	bool	false	if true, the Gateway API ListenerSet flag will be enabled.
enabled	bool	nil	No effect - reserved for use in sub-charting.
env	list	[]	Environment variables for the external-dns container.
excludeDomains	list	[]	Intentionally exclude domains from being managed.
extraArgs	object	{}	Extra arguments to provide to ExternalDNS. An array or map can be used, with maps allowing for value overrides; maps also support slice values to use the same arg multiple times.
extraContainers	list	[]	Extra containers to add to the Deployment.
extraVolumeMounts	list	[]	Extra volume mounts for the external-dns container.
extraVolumes	list	[]	Extra volumes for the Pod.
fullnameOverride	string	nil	Override the full name of the chart.
gatewayNamespace	string	nil	Gateway API gateway namespace to watch. When namespaced=true, setting this value avoids creating any cluster-scoped RBAC (no ClusterRole/ClusterRoleBinding) for Gateway sources.
global.imagePullSecrets	list	[]	Global image pull secrets.
image.pullPolicy	string	"IfNotPresent"	Image pull policy for the external-dns container.
image.repository	string	"registry.k8s.io/external-dns/external-dns"	Image repository for the external-dns container.
image.tag	string	nil	Image tag for the external-dns container, this will default to .Chart.AppVersion if not set.
imagePullSecrets	list	[]	Image pull secrets.
initContainers	list	[]	Init containers to add to the Pod definition.
interval	string	"1m"	Interval for DNS updates.
labelFilter	string	nil	Filter resources queried for endpoints by label selector.
livenessProbe	object	See values.yaml	Liveness probe configuration for the external-dns container.
logFormat	string	"text"	Log format.
logLevel	string	"info"	Log level.
managedRecordTypes	list	[]	Record types to manage (default: A, AAAA, CNAME)
nameOverride	string	nil	Override the name of the chart.
namespaceOverride	string	nil	Override the namespace that chart resources are rendered into. Defaults to the release namespace. Useful when installing the chart as a subchart that should live in its own namespace, separate from the umbrella release namespace.
namespaced	bool	false	if true, ExternalDNS will run in a namespaced scope (Role`` and Rolebinding`` will be namespaced too).
nodeSelector	object	{}	Node labels to match for Pod scheduling.
podAnnotations	object	{}	Annotations to add to the Pod.
podLabels	object	{}	Labels to add to the Pod.
podSecurityContext	object	See values.yaml	Pod security context, this supports full customisation.
policy	string	"upsert-only"	How DNS records are synchronized between sources and providers; available values are create-only, sync, & upsert-only.
priorityClassName	string	nil	Priority class name for the Pod.
provider.name	string	"aws"	ExternalDNS provider name; for the available providers and how to configure them see README.
provider.webhook.args	list	[]	Extra arguments to provide for the webhook container.
provider.webhook.env	list	[]	Environment variables for the webhook container.
provider.webhook.extraVolumeMounts	list	[]	Extra volume mounts for the webhook container.
provider.webhook.image.pullPolicy	string	"IfNotPresent"	Image pull policy for the webhook container.
provider.webhook.image.repository	string	nil	Image repository for the webhook container.
provider.webhook.image.tag	string	nil	Image tag for the webhook container.
provider.webhook.livenessProbe	object	See values.yaml	Liveness probe configuration for the external-dns container.
provider.webhook.readinessProbe	object	See values.yaml	Readiness probe configuration for the webhook container.
provider.webhook.resources	object	{}	Resources for the webhook container.
provider.webhook.securityContext	object	See values.yaml	Pod security context for the webhook container.
provider.webhook.service.port	int	8080	Webhook exposed HTTP port for the service.
provider.webhook.serviceMonitor	object	See values.yaml	Optional Service Monitor configuration for the webhook container.
rbac.additionalPermissions	list	[]	Additional rules to add to the ClusterRole.
rbac.create	bool	true	If true, create a ClusterRole & ClusterRoleBinding with access to the Kubernetes API.
readinessProbe	object	See values.yaml	Readiness probe configuration for the external-dns container.
registry	string	"txt"	Specify the registry for storing ownership and labels. Valid values are txt, aws-sd, dynamodb & noop.
resources	object	{}	Resources for the external-dns container.
revisionHistoryLimit	int	nil	Specify the number of old ReplicaSets to retain to allow rollback of the `Deployment``.
secretConfiguration.data	object	{}	Secret data.
secretConfiguration.enabled	bool	false	If true, create a Secret to store sensitive provider configuration (DEPRECATED).
secretConfiguration.mountPath	string	nil	Mount path for the Secret, this can be templated.
secretConfiguration.subPath	string	nil	Sub-path for mounting the Secret, this can be templated.
securityContext	object	See values.yaml	Security context for the external-dns container.
service.annotations	object	{}	Service annotations.
service.enabled	bool	true	If true, create a Service Kubernetes.
service.ipFamilies	list	[]	Service IP families (e.g. IPv4 and/or IPv6).
service.ipFamilyPolicy	string	nil	Service IP family policy.
service.port	int	7979	Service HTTP port.
serviceAccount.annotations	object	{}	Annotations to add to the service account. Templates are allowed in both the key and the value. Example: example.com/annotation/{{ .Values.nameOverride }}: {{ .Values.nameOverride }}
serviceAccount.automountServiceAccountToken	bool	true	Set this to false to opt out of API credential automounting for the ServiceAccount.
serviceAccount.create	bool	true	If true, create a new ServiceAccount.
serviceAccount.labels	object	{}	Labels to add to the service account.
serviceAccount.name	string	nil	If this is set and serviceAccount.create is true this will be used for the created ServiceAccount name, if set and serviceAccount.create is false then this will define an existing ServiceAccount to use.
serviceMonitor.additionalLabels	object	{}	Additional labels for the ServiceMonitor.
serviceMonitor.annotations	object	{}	Annotations to add to the ServiceMonitor.
serviceMonitor.bearerTokenFile	string	nil	Provide a bearer token file for the ServiceMonitor.
serviceMonitor.enabled	bool	false	If true, create a ServiceMonitor resource to support the Prometheus Operator.
serviceMonitor.interval	string	nil	If set override the Prometheus default interval.
serviceMonitor.metricRelabelings	list	[]	Metric relabel configs to apply to samples before ingestion.
serviceMonitor.namespace	string	nil	If set create the ServiceMonitor in an alternate namespace.
serviceMonitor.relabelings	list	[]	Relabel configs to apply to samples before ingestion.
serviceMonitor.scheme	string	nil	If set overrides the Prometheus default scheme.
serviceMonitor.scrapeTimeout	string	nil	If set override the Prometheus default scrape timeout.
serviceMonitor.targetLabels	list	[]	Provide target labels for the ServiceMonitor.
serviceMonitor.tlsConfig	object	{}	Configure the ServiceMonitor TLS config.
shareProcessNamespace	bool	false	If true, the Pod will have process namespace sharing enabled.
sourceNamespace	string	nil	Source namespace to watch for Kubernetes resources other than Gateway API gateways. Used only when namespaced=true. Defaults to Release.Namespace
sources	list	["service","ingress"]	Kubernetes resources to monitor for DNS entries.
terminationGracePeriodSeconds	int	nil	Termination grace period for the Pod in seconds.
tolerations	list	[]	Node taints which will be tolerated for Pod scheduling.
topologySpreadConstraints	list	[]	Topology spread constraints for Pod scheduling. If an explicit label selector is not provided one will be created from the pod selector labels.
triggerLoopOnEvent	bool	false	If true, triggers run loop on create/update/delete events in addition of regular interval.
txtOwnerId	string	nil	Specify an identifier for this instance of ExternalDNS when using a registry other than noop.
txtPrefix	string	nil	Specify a prefix for the domain names of TXT records created for the txt registry. Mutually exclusive with txtSuffix.
txtSuffix	string	nil	Specify a suffix for the domain names of TXT records created for the txt registry. Mutually exclusive with txtPrefix.
