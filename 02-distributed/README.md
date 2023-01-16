## EJERCICIO 02

### 1 - Creamos las imágenes de docker y las subimos a Docker hub

```
docker build -t almcjmi/lc-todo-front .
docker push almcjmi/lc-todo-front
```

```
docker build -t almcjmi/lc-todo-api .
docker push almcjmi/lc-todo-api
```

### 2 - Habilitamos Ingress controller

```
minikube addons enable ingress
```

### 3 - Creamos los ficheros del paso 1 y aplicamos:

- namespace.yaml (Creamos el namespace ejercicio-02)

```
kubectl apply -f namespace.yaml
```

- deployment.yaml

```
kubectl apply -f paso1/deployment.yaml
```

- service.yaml

```
kubectl apply -f paso1/service.yaml
```

### 3 - Creamos los ficheros del paso 2 y aplicamos:

- configmap.yaml

```
kubectl apply -f paso2/configmap.yaml
```

- deployment.yaml

```
kubectl apply -f paso2/deployment.yaml
```

- service.yaml

```
kubectl apply -f paso2/service.yaml
```

### 4 - Creamos los ficheros del paso 3 y aplicamos:

- ingress.yaml

```
kubectl apply -f paso3/ingress.yaml
```

### 5 - Obtenemos la ip (ADDRESS)

```
kubectl get ingress -n ejercicio-02
```

### 7 - Añadimos al fichero /etc/hosts la ip obtenida

```
<ip-obtenida>   lc-todo.edu
```

### 7 - Accedemos al navegador para ver la aplicación o para ver la api

```
lc-todo.edu
```

```
lc-todo.edu/api
```