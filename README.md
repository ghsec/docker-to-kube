# docker-to-kube command what I need

- show docker images: ```sudo docker images```

- Create deploiment from image: ```sudo kubectl create deployment <appName> --image=<REPOSITORY>```

Example: ```sudo kubectl create deployment grafana --image=grafana/grafana-enterprise```


- Get deployments: ```sudo kubectl get deployment```
- Get pods: ```sudo kubectl get pod -o wide```
