
# Obteniendo Información de Contenedores


## 1. Obtener la dirección IP del contenedor `web`

Para obtener la dirección IP del contenedor `web`, se utilizó el siguiente comando:

### Comando ejecutado:
```bash
sudo docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' web
```

Salida 
```bash
172.17.0.2
```

![Imagen de obtener IP del contenedor web](obtengoIP.png)

## 2. Obtener la redirección de puertos del contenedor `web`

Para obtener la redirección de puertos del contenedor `web`, se utilizó el siguiente comando:

### Comando ejecutado:
```bash
sudo docker port web
```

Salida
```bash
80/tcp -> 0.0.0.0:8181
80/tcp -> [::]:8181
```

![Imagen de redirección de puertos del contenedor web](direccionDePuertos.png)

## 3. Obtener la dirección IP del contenedor `bbdd`

Para obtener la dirección IP del contenedor `bbdd`, se utilizó el siguiente comando:

### Comando ejecutado:
```bash
sudo docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' bbdd
```

Salida
```bash
172.17.0.3
```

![Imagen de obtener IP del contenedor bbdd](ObtengoIPBBDD.png)

## 4. Obtener la redirección de puertos del contenedor `bbdd`

Para obtener la redirección de puertos del contenedor `bbdd`, se utilizó el siguiente comando:

### Comando ejecutado:
```bash
sudo docker port bbdd
```

Salida 
```bash
3306/tcp -> 0.0.0.0:3336
3306/tcp -> [::]:3336
```

![Imagen de redirección de puertos del contenedor bbdd](DireccionPuertosContenedor.png)

