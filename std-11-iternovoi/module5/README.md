# Практическая работа модуля 5
1. Вывод команды `helm list`:
   ```bash
    shoxied@HP-Pavilion:~/Documents/yandex practicum/kube/std-11-iternovoi/module5$ helm list
    NAME             	NAMESPACE          	REVISION	UPDATED                                	STATUS  	CHART             	APP VERSION
    local-chartmuseum	user70vkgdhn6wtk2d8	1       	2026-01-23 14:21:21.105703739 +0700 +07	deployed	chartmuseum-3.10.3	0.16.2     
    nginx            	user70vkgdhn6wtk2d8	1       	2026-01-23 13:03:19.249221703 +0700 +07	deployed	my-chart-0.0.1    	1.0.0      
    podinfo          	user70vkgdhn6wtk2d8	2       	2026-01-25 17:32:14.055441384 +0700 +07	deployed	podinfo-1.0.0     	6.6.3
2. Вывод команды `helm list`:
   ```bash
    USER-SUPPLIED VALUES:
    redis:
      config:
        enabled: false
