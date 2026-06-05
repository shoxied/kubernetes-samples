# Практическая работа модуля 3
1. Вывод команды `kubectl get pod`:
   ```bash
   NAME                           READY   STATUS    RESTARTS   AGE
   details-6c466fcbbf-clfkn       1/1     Running   0          99m
   details-6c466fcbbf-qqgmw       1/1     Running   0          99m
   productpage-7bc74d9879-jv27n   1/1     Running   0          100m
   productpage-7bc74d9879-lnsr6   1/1     Running   0          100m
   ratings-55865b656f-jbrc8       1/1     Running   0          90m
   ratings-55865b656f-x2fr5       1/1     Running   0          90m
   reviews-v1-ff975f587-pwkpw     1/1     Running   0          62m
   reviews-v2-9db85fb4f-h57xs     1/1     Running   0          62m
   reviews-v3-dbf5cc8bc-j8755     1/1     Running   0          99m
2. Вывод команды `kubectl get svc`:
   ```bash
   NAME          TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)    AGE
   details       ClusterIP   10.117.177.104   <none>        9080/TCP   100m
   productpage   ClusterIP   10.117.132.165   <none>        9080/TCP   100m
   ratings       ClusterIP   10.117.140.136   <none>        9080/TCP   100m
   reviews       ClusterIP   10.117.199.248   <none>        9080/TCP   100m
   reviews-v1    ClusterIP   10.117.165.233   <none>        9080/TCP   56m
   reviews-v2    ClusterIP   10.117.172.63    <none>        9080/TCP   56m
   reviews-v3    ClusterIP   10.117.218.179   <none>        9080/TCP   56m
3. Вывод команды `kubectl get networkpolicy`:
   ```bash
   NAME            POD-SELECTOR                                   AGE
   networkpolicy   app in (details,productpage,ratings,reviews)   9m56s