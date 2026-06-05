## Практическое задание 1
1. Команда для сборки образа:
    ```bash
    docker build -t ipcounter .
2. Команда для запуска контейнера:
    ```bash
    docker run -v $(pwd):/data ipcounter:latest java -jar ipcounter-1.0.1.jar /data/ips.txt

## Практическое задание 2
1. Команда для запуска пода:
    ```bash
    kubectl run tomcat-pod --image=tomcat:9.0-jdk21 --restart=Never --port=8080
   Команда для запуска сервиса:
    ```bash
    kubectl expose pod tomcat-pod --name=tomcat-service --port=8080
2. Строка из логов Tomcat:
    ```bash
    22-Nov-2025 18:03:42.772 INFO [main] org.apache.catalina.core.StandardService.startInternal Starting service [Catalina]
3. Заголовок веб-страницы запущенного Tomcat - HTTP Status 404 – Не найдено
4. Значения переменных:
    ```bash
    KUBERNETES_PORT_443_TCP_PROTO=tcp
    ```bash
    JAVA_HOME=/opt/java/openjdk
    ```bash
    LANG=en_US.UTF-8
    ```bash
    CATALINA_HOME=/usr/local/tomcat
    ```bash
    HOSTNAME=tomcat-pod
