# CI/CD Web Demo

Proyecto de demostración de CI/CD con Jenkins, Docker y Docker Compose.

## Estructura del proyecto

```
cicd-web-demo/
├── app/
│   └── index.html          # Aplicación web simple
├── scripts/
│   └── test.sh            # Script de pruebas
├── Dockerfile             # Construcción de imagen Docker
├── docker-compose.yml     # Configuración de staging y producción
├── Jenkinsfile           # Pipeline CI/CD
└── README.md             # Este archivo
```

## Pipeline CI/CD

El Jenkinsfile implementa el siguiente flujo:

1. **Checkout**: Descarga el código del repositorio
2. **Lint/Validación**: Verifica que existan los archivos necesarios
3. **Test**: Ejecuta las pruebas automatizadas
4. **Build**: Construye la imagen Docker para staging
5. **Deploy Staging**: Despliega en el entorno de staging (puerto 8081)
6. **Aprobación Manual**: Espera confirmación para producción
7. **Promoción**: Etiqueta la imagen como producción
8. **Deploy Producción**: Despliega en producción (puerto 8082)

## Acceso a los entornos

- **Staging**: http://localhost:8081
- **Producción**: http://localhost:8082
- **Jenkins**: http://localhost:8080

## Comandos útiles

Ver contenedores corriendo:
```bash
docker ps
```

Ver logs de Jenkins:
```bash
docker logs jenkins
```

Detener todos los servicios:
```bash
docker compose down
```