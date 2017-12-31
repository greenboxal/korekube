# KoreKube

Production ready Kubernetes cluster for Container Linux

KoreKube is meant to be used on AWS and is 100% opinionated.

## Requirements

* CoreOS Container Linux
* Credstash

## Assumptions

* The cluster CA is stored in credstash
* You're using weave-net

## Usage

The package should installed into `/opt/kubekore`. Install the relevant systemd units from `units` dir.

## Configuration

You can change configuration values in `/etc/korekube-env`.

| Name                  | Description                                                 | Default Value                 |
| -                     | -                                                           | -                             |
| `KUBE_API_ENDPOINT`   | Kubernetes API endpoint                                     |                               |
| `CLUSTER_NAME`        | Cluster name, used in several different places              | k8s                           |
| `CLUSTER_POD_CIDR`    | Network that pods should be put into                        | 10.110.0.0/16                 |
| `CLUSTER_SVC_CIDR`    | Network where services VIPs are created                     | 10.100.0.0/16                 |
| `CLUSTER_DNS_IP`      | DNS resolvers for pods                                      | 10.100.0.2                    |
| `SSL_KEY_BITS`        | Key size for SSL certificates issued for the cluster        | 2048                          |
| `SSL_DAYS`            | Expiration days for SSL certificates issued for the cluster | 365                           |
| `HYPERKUBE_IMAGE`     | Hyperkube image                                             | quay.io/coreos/hyperkube      |
| `HYPERKUBE_IMAGE_TAG` | Hyperkube image version                                     | v1.7.11_coreos.0              |
| `NODE_NAME`           | Node name for this kubelet                                  | Private DNS from EC2 metadata |
| `NODE_IP`             | Node private IP                                             | Private IP from EC2 metadata  |
| `NODE_TAINTS`         | Taints to be added                                          |                               |
| `NODE_LABELS`         | Labels to be added                                          |                               |
| `KUBELET_ARGS`        | Extra args to pass to kubelet                               |                               |
| `APISERVER_ARGS`      | Extra args to pass to api-server                            |                               |

