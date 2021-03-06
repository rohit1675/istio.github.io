---
title: kubernetes Config
overview: Generated documentation for Mixer's kubernetes Adapter Configuration Schema

order: 30

layout: docs
type: markdown
---


<a name="rpcAdapter.kubernetes.configIndex"></a>
### Index

* [Params](#adapter.kubernetes.config.Params)
(message)

<a name="adapter.kubernetes.config.Params"></a>
### Params
Configuration parameters for the kubernetes adapter. These params
control the manner in which the kubernetes adapter discovers and
generates values related to pod information.

The adapter works by looking up pod information by UIDs (of the
form: "kubernetes://pod.namespace"). It expects that the UIDs will be
supplied in an input map for three distinct traffic classes (source,
target, and origin).

For all valid UIDs supplied, this adapter generates a map of output
values containing information about the related pods. The generated map
is keyed by value names generated by concatenating a pod identifier
prefix with a value name. For example, for the pod corresponding to a
sourceUID and the output value of pod ip, this adapter will output a map
that includes a key of "sourcePodIP" (assuming parameter defaults).
next field id: 19

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
 </tr>
<a name="adapter.kubernetes.config.Params.kubeconfigPath"></a>
 <tr>
  <td><code>kubeconfigPath</code></td>
  <td>string</td>
  <td><p>File path to discover kubeconfig. For in-cluster configuration, this should be left unset. For local configuration, this should be set to the path of a kubeconfig file that can be used to reach a kubernetes API server.</p><p>Default: "" (unset)</p></td>
 </tr>
<a name="adapter.kubernetes.config.Params.cacheRefreshDuration"></a>
 <tr>
  <td><code>cacheRefreshDuration</code></td>
  <td><a href="https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#duration">Duration</a></td>
  <td><p>Controls the resync period of the kubernetes cluster info cache. The cache will watch for events and every so often completely resync. This controls how frequently the complete resync occurs.</p><p>Default: 5 minutes</p></td>
 </tr>
<a name="adapter.kubernetes.config.Params.sourceUidInputName"></a>
 <tr>
  <td><code>sourceUidInputName</code></td>
  <td>string</td>
  <td><p>Configures how the UID for the source pod for traffic is identified in the input map.</p><p>Default: sourceUID</p></td>
 </tr>
<a name="adapter.kubernetes.config.Params.targetUidInputName"></a>
 <tr>
  <td><code>targetUidInputName</code></td>
  <td>string</td>
  <td><p>Configures how the UID for the target pod for traffic is identified in the input map.</p><p>Default: targetUID</p></td>
 </tr>
<a name="adapter.kubernetes.config.Params.originUidInputName"></a>
 <tr>
  <td><code>originUidInputName</code></td>
  <td>string</td>
  <td><p>Configures how the UID for the origin pod for traffic is identified in the input map.</p><p>Default: originUID</p></td>
 </tr>
<a name="adapter.kubernetes.config.Params.targetServiceInputName"></a>
 <tr>
  <td><code>targetServiceInputName</code></td>
  <td>string</td>
  <td><p>Configures how the identifier for the target service is populated in the input map (if at all). When supplied, this value will be used (after successful normalization) in place of the value derived from the pod cache for the target pod in the generated map of output values.</p><p>Default: targetService</p></td>
 </tr>
<a name="adapter.kubernetes.config.Params.clusterDomainName"></a>
 <tr>
  <td><code>clusterDomainName</code></td>
  <td>string</td>
  <td><p>Configures the cluster domain name to use for service name normalization.</p><p>Default: svc.cluster.local</p></td>
 </tr>
<a name="adapter.kubernetes.config.Params.podLabelForService"></a>
 <tr>
  <td><code>podLabelForService</code></td>
  <td>string</td>
  <td><p>In order to extract the service associated with a source, target, or origin, this adapter relies on pod labels. In particular, it looks for the value of a specific label, as specified by this parameter.</p><p>Default: app</p></td>
 </tr>
<a name="adapter.kubernetes.config.Params.sourcePrefix"></a>
 <tr>
  <td><code>sourcePrefix</code></td>
  <td>string</td>
  <td><p>The prefix used for source pod output value names.</p><p>Default: source</p></td>
 </tr>
<a name="adapter.kubernetes.config.Params.targetPrefix"></a>
 <tr>
  <td><code>targetPrefix</code></td>
  <td>string</td>
  <td><p>The prefix used for target pod output value names.</p><p>Default: target</p></td>
 </tr>
<a name="adapter.kubernetes.config.Params.originPrefix"></a>
 <tr>
  <td><code>originPrefix</code></td>
  <td>string</td>
  <td><p>The prefix used for origin pod output value names.</p><p>Default: origin</p></td>
 </tr>
<a name="adapter.kubernetes.config.Params.labelsValueName"></a>
 <tr>
  <td><code>labelsValueName</code></td>
  <td>string</td>
  <td><p>The value name for the pod labels output value.</p><p>Default: Labels</p></td>
 </tr>
<a name="adapter.kubernetes.config.Params.podNameValueName"></a>
 <tr>
  <td><code>podNameValueName</code></td>
  <td>string</td>
  <td><p>The value name for the pod name output value.</p><p>Default: PodName</p></td>
 </tr>
<a name="adapter.kubernetes.config.Params.podIpValueName"></a>
 <tr>
  <td><code>podIpValueName</code></td>
  <td>string</td>
  <td><p>The value name for the pod ip address output value.</p><p>Default: PodIP</p></td>
 </tr>
<a name="adapter.kubernetes.config.Params.hostIpValueName"></a>
 <tr>
  <td><code>hostIpValueName</code></td>
  <td>string</td>
  <td><p>The value name for the pod host ip address output value.</p><p>Default: HostIP</p></td>
 </tr>
<a name="adapter.kubernetes.config.Params.namespaceValueName"></a>
 <tr>
  <td><code>namespaceValueName</code></td>
  <td>string</td>
  <td><p>The value name for the pod namespace output value.</p><p>Default: Namespace</p></td>
 </tr>
<a name="adapter.kubernetes.config.Params.serviceAccountValueName"></a>
 <tr>
  <td><code>serviceAccountValueName</code></td>
  <td>string</td>
  <td><p>The value name for the pod service account name output value.</p><p>Default: ServiceAccountName</p></td>
 </tr>
<a name="adapter.kubernetes.config.Params.serviceValueName"></a>
 <tr>
  <td><code>serviceValueName</code></td>
  <td>string</td>
  <td><p>The value name for the service output value.</p><p>Default: Service</p></td>
 </tr>
</table>
