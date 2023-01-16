## EJERCICIO 01

### 1 - Creamos la imagen de docker y la subimos a Docker hub

```
docker build -t almcjmi/lc-todo-monolith-front-end .
docker push almcjmi/lc-todo-monolith-front-end
```

### 2 - Creamos los ficheros del paso 1 y aplicamos:

- namespace.yaml (Creamos el namespace ejercicio-01)

```
kubectl apply -f namespace.yaml
```

- configmap.yaml

```
kubectl apply -f paso1/configmap.yaml
```

- storageclass.yaml

```
kubectl apply -f paso1/storageclass.yaml
```

- persistentvolume.yaml

```
kubectl apply -f paso1/persistentvolume.yaml
```

- persistentvolumeclaim.yaml

```
kubectl apply -f paso1/persistentvolumeclaim.yaml
```

- service.yaml

```
kubectl apply -f paso1/service.yaml

```

- Añadimos los datos a la base de datos como indica el ejercicio.

### 3 - Creamos los ficheros del paso 2 y aplicamos:

- configmap.yaml

```
kubectl apply -f paso2/configmap.yaml
```

- deployment.yaml

```
kubectl apply -f paso2/deployment.yaml
```

### 4 - Creamos los ficheros del paso 3 y aplicamos:

- service.yaml

```
kubectl apply -f paso3/service.yaml
```

### 5 - Ejecutamos en otro terminal:

```
minikube tunnel
```

### 6 - Optenemos la ip (EXTERNAL-IP)

```
kubectl get svc -n ejercicio-01
```

### 7 - En el navegador ponemos la ip obtenida anteriormente y el puerto 3000

```
<ip-obtenida>:3000
```