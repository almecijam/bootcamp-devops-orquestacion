## EJERCICIO 00

### 1 - Creamos la imagen de docker y la subimos a Docker hub

```
docker build -t almcjmi/lc-todo-monolith .
docker push almcjmi/lc-todo-monolith
```

### 2 - Creamos los ficheros y aplicamos:

- namespace.yaml (Creamos el namespace ejercicio-00)

```
kubectl apply -f namespace.yaml
```

- deployment.yaml

```
kubectl apply -f deployment.yaml
```

- service.yaml

```
kubectl apply -f service.yaml
```

### 3 - Ejecutamos en otro terminal:

```
minikube tunnel
```

### 4 - Optenemos la ip (EXTERNAL-IP)

```
kubectl get svc -n ejercicio-00
```

### 5 - En el navegador ponemos la ip obtenida anteriormente y el puerto 3000

```
<ip-obtenida>:3000
```
