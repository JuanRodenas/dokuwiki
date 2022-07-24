<p align="center">
  <img src="https://user-images.githubusercontent.com/31465/34380645-bd67f474-eb0b-11e7-8d03-0151c1730654.png" height="29" />
</p>
<p align="center">
  <i>A fast, collaborative, knowledge base for your team built using React and Node.js.<br/>Try out Outline using our hosted version at <a href="https://www.getoutline.com">www.getoutline.com</a>.</i>
  <br/>
  <img width="1640" alt="screenshot" src="https://user-images.githubusercontent.com/380914/110356468-26374600-7fef-11eb-9f6a-f2cc2c8c6590.png">
</p>


### Documentación
<ul>
<p><a href="https://github.com/outline/outline">Github</a></p>
<p><a href="https://app.getoutline.com/share/770a97da-13e5-401e-9f8a-37949c19f97e/">Documentation</a></p>
<p><a href="https://hub.docker.com/r/outlinewiki/outline">Docker Image</a></p>
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
git clone "https://github.com/JuanRodenas/outline.git"
```

### Configuration
Sustituya las variables de entorno en `.env` por las suyas propias, y luego ejecute :

```bash
docker-compose up -d
```
