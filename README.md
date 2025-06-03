# README

```shell
kind version
kind v0.27.0 go1.23.6 darwin/arm64
```

```shell
kind create cluster --config kind.yaml --name sample-app-cluster
kubectl apply -k git@github.com:kubernetes/ingress-nginx.git/deploy/static/provider/kind
```

```shell
docker build -t sample-app:v1 .
kind load docker-image sample-app:v1 --name sample-app-cluster
```

```shell
kubectl apply -f pod.yaml
kubectl apply -f service.yaml
kubectl apply -f ingress.yaml
```

# 動作確認

http://sample-app.lvh.me/
![image](https://github.com/user-attachments/assets/5bd8d7c3-a661-4d6d-b74f-6402a65ea684)
