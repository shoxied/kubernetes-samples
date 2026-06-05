# Практическая работа модуля 3
1. Вывод команды `kubectl get pod`:
   ```bash
   NAME                        READY   STATUS    RESTARTS   AGE
   nginx-cdn-bb86b9cfb-5zl2q   1/1     Running   0          54m
2. Вывод команды `kubectl events`:
   ```bash
   LAST SEEN               TYPE     REASON               OBJECT                                   MESSAGE
   56m                     Normal   Scheduled            Pod/nginx-cdn-bb86b9cfb-5zl2q            Successfully assigned user70vkgdhn6wtk2d8/nginx-cdn-bb86b9cfb-5zl2q to cl1km4cjsm176lltbm3d-axoj
   56m                     Normal   SuccessfulCreate     ReplicaSet/nginx-cdn-bb86b9cfb           Created pod: nginx-cdn-bb86b9cfb-5zl2q
   56m                     Normal   Killing              Pod/nginx-cdn-bb86b9cfb-vtt6m            Stopping container nginx-cdn
   56m                     Normal   Pulling              Pod/nginx-cdn-bb86b9cfb-5zl2q            Pulling image "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest"
   56m                     Normal   Pulled               Pod/nginx-cdn-bb86b9cfb-5zl2q            Successfully pulled image "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest" in 1.382s (1.382s including waiting). Image size: 36345415 bytes.
   56m                     Normal   Created              Pod/nginx-cdn-bb86b9cfb-5zl2q            Created container init-container
   56m                     Normal   Started              Pod/nginx-cdn-bb86b9cfb-5zl2q            Started container init-container
   56m                     Normal   Pulling              Pod/nginx-cdn-bb86b9cfb-5zl2q            Pulling image "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest"
   56m                     Normal   Pulled               Pod/nginx-cdn-bb86b9cfb-5zl2q            Successfully pulled image "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest" in 222ms (222ms including waiting). Image size: 36345415 bytes.
   56m                     Normal   Created              Pod/nginx-cdn-bb86b9cfb-5zl2q            Created container nginx-cdn
   56m                     Normal   Started              Pod/nginx-cdn-bb86b9cfb-5zl2q            Started container nginx-cdn
   50m                     Normal   CreateCertificate    Ingress/nginx-cdn                        Successfully created Certificate "nginx-cdn-secret"
   22m                     Normal   CreateCertificate    Ingress/nginx-cdn                        Successfully created Certificate "nginx-cdn-secret"
   20m                     Normal   DeleteCertificate    Ingress/nginx-cdn                        Successfully deleted unrequired Certificate "nginx-cdn-secret"
   10m                     Normal   Sync                 Ingress/nginx-cdn                        Scheduled for sync
   10m                     Normal   Sync                 Ingress/nginx-cdn                        Scheduled for sync
   9m3s                    Normal   CreateCertificate    Ingress/nginx-cdn                        Successfully created Certificate "nginx-cdn--secret"
   9m3s                    Normal   Generated            Certificate/nginx-cdn--secret            Stored new private key in temporary Secret resource "nginx-cdn--secret-mpbzt"
   9m3s                    Normal   Issuing              Certificate/nginx-cdn--secret            Issuing certificate as Secret does not exist
   9m2s                    Normal   WaitingForApproval   CertificateRequest/nginx-cdn--secret-1   Not signing CertificateRequest until it is Approved
   9m2s                    Normal   WaitingForApproval   CertificateRequest/nginx-cdn--secret-1   Not signing CertificateRequest until it is Approved
   9m2s                    Normal   Requested            Certificate/nginx-cdn--secret            Created new CertificateRequest resource "nginx-cdn--secret-1"
   9m2s                    Normal   WaitingForApproval   CertificateRequest/nginx-cdn--secret-1   Not signing CertificateRequest until it is Approved
   9m2s                    Normal   WaitingForApproval   CertificateRequest/nginx-cdn--secret-1   Not signing CertificateRequest until it is Approved
   9m2s                    Normal   WaitingForApproval   CertificateRequest/nginx-cdn--secret-1   Not signing CertificateRequest until it is Approved
   9m2s                    Normal   cert-manager.io      CertificateRequest/nginx-cdn--secret-1   Certificate request has been approved by cert-manager.io
   9m1s                    Normal   OrderPending         CertificateRequest/nginx-cdn--secret-1   Waiting on certificate issuance from order user70vkgdhn6wtk2d8/nginx-cdn--secret-1-2032110405: ""
   9m1s                    Normal   OrderCreated         CertificateRequest/nginx-cdn--secret-1   Created Order resource user70vkgdhn6wtk2d8/nginx-cdn--secret-1-2032110405
   8m57s                   Normal   CertificateIssued    CertificateRequest/nginx-cdn--secret-1   Certificate fetched from issuer successfully
   8m57s                   Normal   Complete             Order/nginx-cdn--secret-1-2032110405     Order completed successfully
   8m56s                   Normal   Issuing              Certificate/nginx-cdn--secret            The certificate has been successfully issued
   8m33s (x2 over 9m4s)    Normal   Sync                 Ingress/nginx-cdn                        Scheduled for sync
   8m33s (x2 over 9m4s)    Normal   Sync                 Ingress/nginx-cdn                        Scheduled for sync
3. Вывод команды `kubectl describe pod nginx-cdn-bb86b9cfb-5zl2q`:
   ```bash
   Name:             nginx-cdn-bb86b9cfb-5zl2q
   Namespace:        user70vkgdhn6wtk2d8
   Priority:         0
   Service Account:  default
   Node:             cl1km4cjsm176lltbm3d-axoj/10.129.0.70
   Start Time:       Mon, 19 Jan 2026 02:07:15 +0700
   Labels:           app=nginx-cdn
   pod-template-hash=bb86b9cfb
   Annotations:      cni.projectcalico.org/containerID: 65d5631738c374e3f6cd80a9596fca4d939e9e66334d4b6126d108e07619f594
   cni.projectcalico.org/podIP: 10.115.143.80/32
   cni.projectcalico.org/podIPs: 10.115.143.80/32
   kubernetes.io/limit-ranger:
   LimitRanger plugin set: memory request for container nginx-cdn; memory limit for container nginx-cdn; memory request for init container in...
   Status:           Running
   IP:               10.115.143.80
   IPs:
   IP:           10.115.143.80
   Controlled By:  ReplicaSet/nginx-cdn-bb86b9cfb
   Init Containers:
   init-container:
   Container ID:  containerd://f736415f78fa3e40a60f6f17058bbb761d8b336cd7b9a5de2c05ca0dba9b73c9
   Image:         cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest
   Image ID:      cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn@sha256:689448a093acba97d4cdf8294acc14cc48af77a0a951972339787700023819b7
   Port:          <none>
   Host Port:     <none>
   Command:
   /bin/sh
   -c
   Args:
   /download.sh

    State:          Terminated
      Reason:       Completed
      Exit Code:    0
      Started:      Mon, 19 Jan 2026 02:07:18 +0700
      Finished:     Mon, 19 Jan 2026 02:07:18 +0700
    Ready:          True
    Restart Count:  0
    Limits:
      cpu:     2
      memory:  3000Mi
    Requests:
      cpu:     200m
      memory:  200Mi
    Environment:
      URL:  https://code.s3.yandex.net/Kubernetes/barsik.jpg
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-gt2tn (ro)
      /var/www/html/ from shared-data (rw)
   Containers:
   nginx-cdn:
   Container ID:  containerd://77d8dcfa2ee1188180e6cd3f9953911f160adf5fcca100ac90603dec4e8b99a7
   Image:         cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest
   Image ID:      cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn@sha256:689448a093acba97d4cdf8294acc14cc48af77a0a951972339787700023819b7
   Port:          80/TCP (http)
   Host Port:     0/TCP (http)
   Command:
   nginx
   -g
   daemon off;
   State:          Running
   Started:      Mon, 19 Jan 2026 02:07:20 +0700
   Ready:          True
   Restart Count:  0
   Limits:
   cpu:     2
   memory:  3000Mi
   Requests:
   cpu:        200m
   memory:     200Mi
   Liveness:     http-get http://:80/ delay=30s timeout=5s period=10s #success=1 #failure=3
   Readiness:    http-get http://:80/.done delay=10s timeout=3s period=5s #success=1 #failure=3
   Environment:  <none>
   Mounts:
   /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-gt2tn (ro)
   /var/www/html/ from shared-data (rw)
   Conditions:
   Type                        Status
   PodReadyToStartContainers   True
   Initialized                 True
   Ready                       True
   ContainersReady             True
   PodScheduled                True
   Volumes:
   shared-data:
   Type:       EmptyDir (a temporary directory that shares a pod's lifetime)
   Medium:     
   SizeLimit:  <unset>
   kube-api-access-gt2tn:
   Type:                    Projected (a volume that contains injected data from multiple sources)
   TokenExpirationSeconds:  3607
   ConfigMapName:           kube-root-ca.crt
   Optional:                false
   DownwardAPI:             true
   QoS Class:                   Burstable
   Node-Selectors:              <none>
   Tolerations:                 node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
   node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
   Events:
   Type    Reason     Age   From               Message
     ----    ------     ----  ----               -------
   Normal  Scheduled  59m   default-scheduler  Successfully assigned user70vkgdhn6wtk2d8/nginx-cdn-bb86b9cfb-5zl2q to cl1km4cjsm176lltbm3d-axoj
   Normal  Pulling    59m   kubelet            Pulling image "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest"
   Normal  Pulled     59m   kubelet            Successfully pulled image "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest" in 1.382s (1.382s including waiting). Image size: 36345415 bytes.
   Normal  Created    59m   kubelet            Created container init-container
   Normal  Started    59m   kubelet            Started container init-container
   Normal  Pulling    59m   kubelet            Pulling image "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest"
   Normal  Pulled     59m   kubelet            Successfully pulled image "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest" in 222ms (222ms including waiting). Image size: 36345415 bytes.
   Normal  Created    59m   kubelet            Created container nginx-cdn
   Normal  Started    59m   kubelet            Started container nginx-cdn 
4. Вывод команды `kubectl get po nginx-cdn-bb86b9cfb-5zl2q -o json`:
   ```bash
   {
    "apiVersion": "v1",
    "kind": "Pod",
    "metadata": {
        "annotations": {
            "cni.projectcalico.org/containerID": "65d5631738c374e3f6cd80a9596fca4d939e9e66334d4b6126d108e07619f594",
            "cni.projectcalico.org/podIP": "10.115.143.80/32",
            "cni.projectcalico.org/podIPs": "10.115.143.80/32",
            "kubernetes.io/limit-ranger": "LimitRanger plugin set: memory request for container nginx-cdn; memory limit for container nginx-cdn; memory request for init container init-container; memory limit for init container init-container"
        },
        "creationTimestamp": "2026-01-18T19:07:15Z",
        "generateName": "nginx-cdn-bb86b9cfb-",
        "labels": {
            "app": "nginx-cdn",
            "pod-template-hash": "bb86b9cfb"
        },
        "name": "nginx-cdn-bb86b9cfb-5zl2q",
        "namespace": "user70vkgdhn6wtk2d8",
        "ownerReferences": [
            {
                "apiVersion": "apps/v1",
                "blockOwnerDeletion": true,
                "controller": true,
                "kind": "ReplicaSet",
                "name": "nginx-cdn-bb86b9cfb",
                "uid": "6859bc62-c16e-4752-b147-136748b7290c"
            }
        ],
        "resourceVersion": "579181529",
        "uid": "1e54cc2d-cb81-4913-b871-0559c9dc95fc"
    },
    "spec": {
        "containers": [
            {
                "command": [
                    "nginx",
                    "-g",
                    "daemon off;"
                ],
                "image": "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest",
                "imagePullPolicy": "Always",
                "livenessProbe": {
                    "failureThreshold": 3,
                    "httpGet": {
                        "path": "/",
                        "port": 80,
                        "scheme": "HTTP"
                    },
                    "initialDelaySeconds": 30,
                    "periodSeconds": 10,
                    "successThreshold": 1,
                    "timeoutSeconds": 5
                },
                "name": "nginx-cdn",
                "ports": [
                    {
                        "containerPort": 80,
                        "name": "http",
                        "protocol": "TCP"
                    }
                ],
                "readinessProbe": {
                    "failureThreshold": 3,
                    "httpGet": {
                        "path": "/.done",
                        "port": 80,
                        "scheme": "HTTP"
                    },
                    "initialDelaySeconds": 10,
                    "periodSeconds": 5,
                    "successThreshold": 1,
                    "timeoutSeconds": 3
                },
                "resources": {
                    "limits": {
                        "cpu": "2",
                        "memory": "3000Mi"
                    },
                    "requests": {
                        "cpu": "200m",
                        "memory": "200Mi"
                    }
                },
                "terminationMessagePath": "/dev/termination-log",
                "terminationMessagePolicy": "File",
                "volumeMounts": [
                    {
                        "mountPath": "/var/www/html/",
                        "name": "shared-data"
                    },
                    {
                        "mountPath": "/var/run/secrets/kubernetes.io/serviceaccount",
                        "name": "kube-api-access-gt2tn",
                        "readOnly": true
                    }
                ]
            }
        ],
        "dnsPolicy": "ClusterFirst",
        "enableServiceLinks": true,
        "initContainers": [
            {
                "args": [
                    "/download.sh\n"
                ],
                "command": [
                    "/bin/sh",
                    "-c"
                ],
                "env": [
                    {
                        "name": "URL",
                        "value": "https://code.s3.yandex.net/Kubernetes/barsik.jpg"
                    }
                ],
                "image": "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest",
                "imagePullPolicy": "Always",
                "name": "init-container",
                "resources": {
                    "limits": {
                        "cpu": "2",
                        "memory": "3000Mi"
                    },
                    "requests": {
                        "cpu": "200m",
                        "memory": "200Mi"
                    }
                },
                "terminationMessagePath": "/dev/termination-log",
                "terminationMessagePolicy": "File",
                "volumeMounts": [
                    {
                        "mountPath": "/var/www/html/",
                        "name": "shared-data"
                    },
                    {
                        "mountPath": "/var/run/secrets/kubernetes.io/serviceaccount",
                        "name": "kube-api-access-gt2tn",
                        "readOnly": true
                    }
                ]
            }
        ],
        "nodeName": "cl1km4cjsm176lltbm3d-axoj",
        "preemptionPolicy": "PreemptLowerPriority",
        "priority": 0,
        "restartPolicy": "Always",
        "schedulerName": "default-scheduler",
        "securityContext": {},
        "serviceAccount": "default",
        "serviceAccountName": "default",
        "terminationGracePeriodSeconds": 30,
        "tolerations": [
            {
                "effect": "NoExecute",
                "key": "node.kubernetes.io/not-ready",
                "operator": "Exists",
                "tolerationSeconds": 300
            },
            {
                "effect": "NoExecute",
                "key": "node.kubernetes.io/unreachable",
                "operator": "Exists",
                "tolerationSeconds": 300
            }
        ],
        "volumes": [
            {
                "emptyDir": {},
                "name": "shared-data"
            },
            {
                "name": "kube-api-access-gt2tn",
                "projected": {
                    "defaultMode": 420,
                    "sources": [
                        {
                            "serviceAccountToken": {
                                "expirationSeconds": 3607,
                                "path": "token"
                            }
                        },
                        {
                            "configMap": {
                                "items": [
                                    {
                                        "key": "ca.crt",
                                        "path": "ca.crt"
                                    }
                                ],
                                "name": "kube-root-ca.crt"
                            }
                        },
                        {
                            "downwardAPI": {
                                "items": [
                                    {
                                        "fieldRef": {
                                            "apiVersion": "v1",
                                            "fieldPath": "metadata.namespace"
                                        },
                                        "path": "namespace"
                                    }
                                ]
                            }
                        }
                    ]
                }
            }
        ]
    },
    "status": {
        "conditions": [
            {
                "lastProbeTime": null,
                "lastTransitionTime": "2026-01-18T19:07:18Z",
                "status": "True",
                "type": "PodReadyToStartContainers"
            },
            {
                "lastProbeTime": null,
                "lastTransitionTime": "2026-01-18T19:07:19Z",
                "status": "True",
                "type": "Initialized"
            },
            {
                "lastProbeTime": null,
                "lastTransitionTime": "2026-01-18T19:07:31Z",
                "status": "True",
                "type": "Ready"
            },
            {
                "lastProbeTime": null,
                "lastTransitionTime": "2026-01-18T19:07:31Z",
                "status": "True",
                "type": "ContainersReady"
            },
            {
                "lastProbeTime": null,
                "lastTransitionTime": "2026-01-18T19:07:15Z",
                "status": "True",
                "type": "PodScheduled"
            }
        ],
        "containerStatuses": [
            {
                "containerID": "containerd://77d8dcfa2ee1188180e6cd3f9953911f160adf5fcca100ac90603dec4e8b99a7",
                "image": "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest",
                "imageID": "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn@sha256:689448a093acba97d4cdf8294acc14cc48af77a0a951972339787700023819b7",
                "lastState": {},
                "name": "nginx-cdn",
                "ready": true,
                "restartCount": 0,
                "started": true,
                "state": {
                    "running": {
                        "startedAt": "2026-01-18T19:07:20Z"
                    }
                },
                "volumeMounts": [
                    {
                        "mountPath": "/var/www/html/",
                        "name": "shared-data"
                    },
                    {
                        "mountPath": "/var/run/secrets/kubernetes.io/serviceaccount",
                        "name": "kube-api-access-gt2tn",
                        "readOnly": true,
                        "recursiveReadOnly": "Disabled"
                    }
                ]
            }
        ],
        "hostIP": "10.129.0.70",
        "hostIPs": [
            {
                "ip": "10.129.0.70"
            }
        ],
        "initContainerStatuses": [
            {
                "containerID": "containerd://f736415f78fa3e40a60f6f17058bbb761d8b336cd7b9a5de2c05ca0dba9b73c9",
                "image": "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest",
                "imageID": "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn@sha256:689448a093acba97d4cdf8294acc14cc48af77a0a951972339787700023819b7",
                "lastState": {},
                "name": "init-container",
                "ready": true,
                "restartCount": 0,
                "started": false,
                "state": {
                    "terminated": {
                        "containerID": "containerd://f736415f78fa3e40a60f6f17058bbb761d8b336cd7b9a5de2c05ca0dba9b73c9",
                        "exitCode": 0,
                        "finishedAt": "2026-01-18T19:07:18Z",
                        "reason": "Completed",
                        "startedAt": "2026-01-18T19:07:18Z"
                    }
                },
                "volumeMounts": [
                    {
                        "mountPath": "/var/www/html/",
                        "name": "shared-data"
                    },
                    {
                        "mountPath": "/var/run/secrets/kubernetes.io/serviceaccount",
                        "name": "kube-api-access-gt2tn",
                        "readOnly": true,
                        "recursiveReadOnly": "Disabled"
                    }
                ]
            }
        ],
        "phase": "Running",
        "podIP": "10.115.143.80",
        "podIPs": [
            {
                "ip": "10.115.143.80"
            }
        ],
        "qosClass": "Burstable",
        "startTime": "2026-01-18T19:07:15Z"
    }
   }
