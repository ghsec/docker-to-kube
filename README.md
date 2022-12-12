# docker-to-kube - Notes

- show docker images: ```sudo docker images```

- Create deploiment from image: ```sudo kubectl create deployment <appName> --image=<REPOSITORY>```

Example: ```sudo kubectl create deployment grafana --image=grafana/grafana-enterprise```


- Get deployments: ```sudo kubectl get deployment```
- Get pods: ```sudo kubectl get pod -o wide```

### kubeshark 
command : ```kubectl edit -n kubeshark svc kubeshark-api-server```

config example:

```
apiVersion: v1
kind: Service
metadata:
creationTimestamp: "2022-11-27T07:37:32Z"
labels:
app.kubernetes.io/created-by: kubeshark-cli
app.kubernetes.io/managed-by: kubeshark
name: kubeshark-api-server
namespace: kubeshark
resourceVersion: "11119"
uid: 40b7a925-c3c3-4db3-84bb-aadcc925af30
spec:
clusterIP: 10.96.77.239
clusterIPs:

    10.96.77.239
    externalTrafficPolicy: Cluster   
    internalTrafficPolicy: Cluster
    ipFamilies:
    IPv4
    ipFamilyPolicy: SingleStack
    ports:
    name: api
    nodePort: 31113
    port: 80
    protocol: TCP
    targetPort: 8899
    selector:
    app: kubeshark-api-server
    sessionAffinity: None
    type: NodePort
    status:
    loadBalancer: {}
```


### Expose external ip address
- Create a Service object that exposes the deployment:

```
kubectl expose deployment hello-world --type=LoadBalancer --name=my-service
```

- Display information about the Service:

```
kubectl get services my-service
```

