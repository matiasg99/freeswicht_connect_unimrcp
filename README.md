# freeswitch_connect_unimrcp

Este proyecto utiliza Docker Compose para levantar un entorno con dos servicios principales:

- **freeswitch**: Servidor de telefonía basado en FreeSWITCH, configurado para conectarse a una base de datos PostgreSQL y preparado para integración con SignalWire.
- **unimrcp**: Servidor UniMRCP para procesamiento de voz (ASR/TTS) compatible con FreeSWITCH.

## Estructura del proyecto
- `docker-compose.yml`: Orquestación de los servicios.
- `Dockerfile.freeswitch`: Imagen personalizada de FreeSWITCH.
- `Dockerfile.unimrcp`: Imagen personalizada de UniMRCP.
- `conf/`: Archivos de configuración de FreeSWITCH.
- `mod/`, `scripts/`: Módulos y scripts adicionales.

## Requisitos previos
- Docker y Docker Compose instalados.
- Variables de entorno `SIGNALWIRE_LOGIN` y `SIGNALWIRE_PASSWORD` configuradas si se usa SignalWire.

## Comandos principales

### Construir las imágenes
```fish
docker compose build
```

### Levantar los servicios
```fish
docker compose up -d
```

### Ver logs de un servicio
```fish
docker compose logs -f freeswitch
```

### Detener los servicios
```fish
docker compose down
```

## Notas
- Los puertos expuestos pueden modificarse en `docker-compose.yml` según necesidad.
- La red interna `freeswitch_unimrcp_net` conecta ambos servicios.
- Para personalizar configuraciones, edite los archivos en `conf/`.
