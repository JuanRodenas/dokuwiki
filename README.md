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


## Configuración docker
Para una instalación manual de producción auto-alojada estos son los pasos recomendados:
1. Primero configurar los servidores Redis y Postgres, esto está fuera del alcance de la guía.
2.Descargue la última imagen oficial de Docker, las nuevas versiones están disponibles a mediados de cada mes:
`docker pull outlinewiki/outline`
3. Utilizando el .env.sample como referencia, establezca las variables necesarias en su entorno de producción. Puedes exportar las variables de entorno directamente, o crear un archivo .env y pasarlo a la imagen docker así
`docker run --env-file=.env outlinewiki/outline`
4. Configure la base de datos con yarn db:migrate. Production asume una conexión SSL a la base de datos por defecto, si Postgres está en la misma máquina y no es SSL puedes migrar con yarn db:migrate --env=production-ssl-disabled, por ejemplo:
`docker run --rm outlinewiki/outline yarn db:migrate`
5. Inicie el contenedor:
`docker run outlinewiki/outline`
6. Visita http://you_server_ip:3000 y deberías poder ver la página de Outline
7. El número de puerto se puede cambiar usando la variable de entorno PORT
`(Opcional) Puedes añadir un nginx u otro proxy inverso para servir tu instancia de Outline para una URL limpia sin el número de puerto, soportar SSL, etc.`

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
