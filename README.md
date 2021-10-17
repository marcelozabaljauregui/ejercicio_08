# Ejercicio 07

## Versión 2 archivos

* configmap.yaml
* mnzpingapp.yaml

### Ejecución

Primero el configmap
```
kubectl apply -f configmap.yaml
```
Segundo la aplicación
```
kubectl apply -f mnzpingapp.yaml
```
En caso de omitir el primer paso los contenedores queran en este estado:

```
mzabaljauregui@ubuntu:~/k8s_curso_arba/ejercicio_07$ kubectl -n arba get pods
NAME                       READY   STATUS                       RESTARTS   AGE
pingapp-78d44c7496-5479w   0/1     CreateContainerConfigError   0          4s
pingapp-78d44c7496-g9h9n   0/1     CreateContainerConfigError   0          4s
pingapp-78d44c7496-m7845   0/1     CreateContainerConfigError   0          4s
```
___
_Aclaracion_ : no se usa el comando con el -n arba para el despliegue porque esta incluido en la METADATA de los archivos YAML.
___

## Versión 1 archivo

Podemos poner ambos archivos en uno para evitar el problema anterior

* mnzpingapp-completo.yam

### Ejecución 

```
kubectl apply -f mnzpingapp-completo.yaml
```
