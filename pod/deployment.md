## deployment

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 3  # 副本数量
  selector:    # 选择器，如何选择pod
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:  # pod 的labels
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.15.4
        ports:
        - containerPort: 80
```