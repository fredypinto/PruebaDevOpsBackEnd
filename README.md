# PruebaDevOpsBackEnd
1. CI:
se integro el codigo fuente con la herramienta AzureDevOps, alli lo que se hizo fue:
 - crear el pipeline de integracion continua, mediante una serie de tarea generar un artefacto o entrgable para su despliegue.
 el archivo del pipeline se encuentra en la siguente ruta [pipelineCIyml](https://github.com/fredypinto/PruebaDevOpsBackEnd/blob/main/azure-pipelines.yml)
 
2. CD:
 - configurar la maquina docker para el despliegue de la aplicacion
 - construir archivos Dockerfile y docker-compose para la compilacion y despliego de la imagen:
     . la configuracion del Dockerfile es:
      - como base netcore 5.0
      - copia los archivos generados por CI a la ruta de trabajo App 
      - arranca la aplicacion indicandole la dll a ejecutar
     . la configuracion del docker-compose:
      - se define el servicio 
      - nombre de contenedor
      - nombre de la imagen con la cual correra el contenedor
      - puertos
     . los arvhivos estan en la sigueinte ruta: [Archivos-docker](https://github.com/fredypinto/PruebaDevOpsBackEnd/tree/main/DockerFile)
 - crear el pipeline de despliegue, en donde mediante conexion via ssh el pipeline copia los artefactos generados por CI y seguido compila la imagen y despliega el  contenedor.
   . los archivos de CD estan en : [Archivos-CD](https://github.com/fredypinto/PruebaDevOpsBackEnd/blob/main/BackEnd-CD.json)
   