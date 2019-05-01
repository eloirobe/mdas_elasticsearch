[![CircleCI](https://circleci.com/gh/eloirobe/mdas_elasticsearch.svg?style=svg)](https://circleci.com/gh/eloirobe/mdas_elasticsearch)

# MDAS Bases de datos no estructuradas - Elasticsearch <img src="https://images.contentstack.io/v3/assets/bltefdd0b53724fa2ce/blt6ae3d6980b5fd629/5bbca1d1af3a954c36f95ed3/logo-elastic.svg" width="100"/>
Bienvenidos a la imagen de Elasticsearch para a la asignatura de Bases de datos no estructuradas del master [Máster en Desarrollo y Arquitectura de Software (MDAS)](https://www.salleurl.edu/es/estudios/master-en-desarrollo-y-arquitectura-software)

Para arrancar el Elasticsearch y empezar a utilizar la imagen de docker realizar lo siguiente:

*Requisitos previo tener instalado docker*

1) Clonar el repositorio
```bash
git clone https://github.com/eloirobe/mdas_elasticsearch.git
```
2) Arrancar la imagen de docker
```
cd mdas_elasticsearch
## En modo stdout
docker-compose up
## En modo silencioso
docker-compose up -d
```
3) Una vez haya arrancado entrar en el navegador a esta url: [http://localhost:5601](http://localhost:5601)
4) Ir al apartado de Stack Monitoring y activar el Monitoring
5) Ir a Dev Tools y ejecutar
```
PUT /_snapshot/dataBackup
{
  "type": "fs",
  "settings": {
    "location": "/usr/share/dataBackup",
    "compress": true
  }
}
POST /_snapshot/dataBackup/snapshot_1/_restore
```

6) En Monitoring > Índices veréis creados dos índices.

## Dataset Utilizados

- [https://www.kaggle.com/datafiniti/consumer-reviews-of-amazon-products](https://www.kaggle.com/datafiniti/consumer-reviews-of-amazon-products)

- [https://data.cityofnewyork.us/Health/DOHMH-New-York-City-Restaurant-Inspection-Results/43nn-pn8j](https://data.cityofnewyork.us/Health/DOHMH-New-York-City-Restaurant-Inspection-Results/43nn-pn8j)