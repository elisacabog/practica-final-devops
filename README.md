<header>
# Práctica Final de DevOps
</header>

Este proyecto forma parte de la práctica final del curso de DevOps, donde se ha implementado un flujo completo de integración y despliegue continuo (CI/CD) utilizando GitHub Actions y Docker.

## Estructura
- `index.html`: Archivo HTML que se sirve con Nginx
- `Dockerfile`: Define una imagen basada en nginx:1.24-alpine
- `.github/workflows/build.yml`: Automatiza el build y push de la imagen a Docker Hub

## CI/CD
El flujo automatizado:
- Se ejecuta en cada push a `master` y en cada pull request
- Construye la imagen Docker con el contenido del repositorio
- Autentica contra Docker Hub usando secretos
- Publica automáticamente la imagen con etiquetas generadas

## Imagen disponible en Docker Hub
[Ver en Docker Hub](https://hub.docker.com/r/elisacabo/practica-final-devops)

```bash
docker pull elisacabo/practica-final-devops:master
docker run -d -p 8080:80 elisacabo/practica-final-devops:master
