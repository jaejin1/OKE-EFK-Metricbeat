# OKE-EFK-Metricbeat HELM Chart
This repo is to store the HELM Chart for deploying EFK on OKE

* This will help you to install a complete logging solution for Kubernetes nodes. This is specifically written for Oracle Kubernetes Engine aka OKE. Elasticsearch in this case is not Persistent, that persistence will be delivered later on.

# Now Clone the Github and do the Helm Install.

$ git clone https://github.com/stretchcloud/OKE-EFK-Metricbeat

$ cd OKE-EFK-Metricbeat

$ helm install .


## Installing the Chart with your choice of Release Name

To install the chart with the release name oke-efk-release:

$ helm install --name oke-efk-release .


## Uninstalling the Chart

To uninstall/delete the oke-efk-release deployment:

$ helm delete oke-efk-release


# The command removes all the Kubernetes components associated with the chart and deletes the release.


## Configuration

### Kibana

| Parameter                  | Description                         | Default                                                 |
|----------------------------|-------------------------------------|---------------------------------------------------------|
| `rbac.enabled` | Enables RBAC | `true` |
| `kibana.replicaCount`                 | Number of Kibana nodes | `1` |
| `kibana.image.repository`         | Image repository | `docker.elastic.co/kibana/kibana` |
| `kibana.image.tag`                | Image tag. | `6.2.4`|
| `kibana.image.pullPolicy`         | Image pull policy | `IfNotPresent` |
| `kibana.service.type`             | Kubernetes service type | `LoadBalancer` |
| `kibana.service.port`             | Kubernetes port where service is exposed| `5601` |
| `kibana.ingress.enabled`          | Enables Ingress | `false` |
| `kibana.ingress.annotations`      | Ingress annotations | `{}` |
| `kibana.ingress.path`           | Custom path                       | `/`
| `kibana.ingress.hosts`            | Ingress accepted hostnames | `[kibana.dev]` |
| `kibana.ingress.tls`              | Ingress TLS configuration | `[]` |
| `kibana.resources.limits.cpu`                | CPU resource limits | `1000m` |
| `kibana.resources.requests.cpu`                | CPU resource requests | `100m` |
| `kibana.nodeSelector`             | Node labels for pod assignment | `{}` |
| `kibana.tolerations`              | Toleration labels for pod assignment | `[]` |
| `kibana.affinity`                 | Affinity settings for pod assignment | `{}` |
| `elasticsearch.replicaCount`                 | Number of ElasticSearch nodes | `1` |
| `elasticsearch.image.repository`         | Image repository | `docker.elastic.co/elasticsearch/elasticsearch` |
| `elasticsearch.image.tag`                | Image tag. | `6.2.4`|
| `elasticsearch.image.pullPolicy`         | Image pull policy | `IfNotPresent` |
| `elasticsearch.service.type`             | Kubernetes service type | `ClusterIP` |
| `elasticsearch.service.port`             | Kubernetes port where service is exposed| `9200` |
| `elasticsearch.resources.limits.cpu`                | CPU resource limits | `1000m` |
| `elasticsearch.resources.requests.cpu`                | CPU resource requests | `100m` |
| `elasticsearch.nodeSelector`             | Node labels for pod assignment | `{}` |
| `elasticsearch.tolerations`              | Toleration labels for pod assignment | `[]` |
| `elasticsearch.affinity`                 | Affinity settings for pod assignment | `{}` |
| `fluentdElasticsearch.replicaCount`                 | Number of ElasticSearch nodes | `1` |
| `fluentdElasticsearch.image.repository`         | Image repository | `k8s.gcr.io/fluentd-elasticsearch` |
| `fluentdElasticsearch.image.tag`                | Image tag. | `v2.0.4`|
| `fluentdElasticsearch.image.pullPolicy`         | Image pull policy | `IfNotPresent` |
| `fluentdElasticsearch.service.type`             | Kubernetes service type | `ClusterIP` |
| `fluentdElasticsearch.service.port`             | Kubernetes port where service is exposed| `9200` |
| `fluentdElasticsearch.resources.limits.memory`                | Mem resource limits | `500Mi` |
| `fluentdElasticsearch.resources.requests.cpu`                | CPU resource requests | `100m` |
| `fluentdElasticsearch.resources.requests.memory`                | Mem resource requests | `200Mi` |
| `fluentdElasticsearch.nodeSelector`             | Node labels for pod assignment | `{}` |
| `fluentdElasticsearch.tolerations`              | Toleration labels for pod assignment | `[]` |
| `fluentdElasticsearch.affinity`                 | Affinity settings for pod assignment | `{}` |


# TODO

* [ ] - Add persistence to elasticsearch (possibly Kibana as well)


