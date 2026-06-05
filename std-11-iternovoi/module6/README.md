# Практическая работа модуля 6
1. Вывод команды `kubectl get events --field-selector involvedObject.kind=HorizontalPodAutoscaler --sort-by=.lastTimestamp`:
   ```bash
    9m40s       Normal   SuccessfulRescale   horizontalpodautoscaler/test-app-hpa   New size: 3; reason: cpu resource utilization (percentage of request) above target
    8m40s       Normal   SuccessfulRescale   horizontalpodautoscaler/test-app-hpa   New size: 4; reason: cpu resource utilization (percentage of request) above target
    8m25s       Normal   SuccessfulRescale   horizontalpodautoscaler/test-app-hpa   New size: 5; reason: cpu resource utilization (percentage of request) above target
    6m39s       Normal   SuccessfulRescale   horizontalpodautoscaler/test-app-hpa   New size: 6; reason: cpu resource utilization (percentage of request) above target
    3m54s       Normal   SuccessfulRescale   horizontalpodautoscaler/test-app-hpa   New size: 5; reason: All metrics below target
    2m53s       Normal   SuccessfulRescale   horizontalpodautoscaler/test-app-hpa   New size: 4; reason: All metrics below target
    113s        Normal   SuccessfulRescale   horizontalpodautoscaler/test-app-hpa   New size: 3; reason: All metrics below target
    53s         Normal   SuccessfulRescale   horizontalpodautoscaler/test-app-hpa   New size: 2; reason: All metrics below target
