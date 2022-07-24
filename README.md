## docuwiki
El wiki y la base de conocimientos más rápidos para equipos en crecimiento. Hermosa, rica en características y compatible con Markdown.
 
    

## About
<p align="center">
  <img src="https://github.com/JuanRodenas/dokuwiki/blob/main/dokuwikilogo.png"
       width="300"/>
</p>

<p align="center">
  <img src="https://logos-world.net/wp-content/uploads/2021/02/Docker-Symbol.png" 
       width="300"/>
</p>


### Documentación
<ul>
<p><a href="https://github.com/linuxserver/docker-dokuwiki">Github</a></p>
<p><a href="https://docs.linuxserver.io/images/docker-dokuwiki">Documentation</a></p>
<p><a href="https://hub.docker.com/r/linuxserver/dokuwiki">Docker Image</a></p>
</ul>


## Arquitecturas compatibles
Las arquitecturas soportadas por esta imagen son:

| Architecture | Available | Tag |
| :----: | :----: | ---- |
| x86-64 | ✅ | amd64-\<version tag\> |
| arm64 | ✅ | arm64v8-\<version tag\> |
| armhf| ✅ | arm32v7-\<version tag\> |

## Parámetros
Los parámetros del docker-compose:

| Parameter | Function |
| :----: | --- |
| `-p 80` | Application HTTP Port |
| `-p 443` | #optional Application HTTPS Port |
| `-e PUID=1000` | for UserID - see below for explanation |
| `-e PGID=1000` | for GroupID - see below for explanation |
| `-e TZ=Europe/London` | Specify a timezone to use EG Europe/London. |
| `-v /config` | Configuration files. |

## Files
- Creamos carpeta en el directorio de persistencia:
```
mkdir filerun filerun/html filerun/user-files filerun/db
cd filerun
```
- Descargamos el repositorio:
```
git clone "https://github.com/JuanRodenas/docuwiki.git"
```

### Configuration
Sustituya las variables de entorno en `.env` por las suyas propias, y luego ejecute :

```bash
docker-compose up -d
```
