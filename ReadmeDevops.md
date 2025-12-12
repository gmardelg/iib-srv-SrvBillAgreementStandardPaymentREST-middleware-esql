## TABLA DE CONTENIDO
- [1 CONFIGURACIONES](#1-CONFIGURACIONES)
  - [CONFIGURACIONES INICIALES](#CONFIGURACIONES-INICIALES)
  - [CREACIÓN Y CONFIGURACIÓN LLAVE GPG](#CREACIÓN-Y-CONFIGURACIÓN-LLAVE-GPG)
- [2 ESTRATEGIAS DE RAMIFICACIÓN](#2-ESTRATEGIAS-DE-RAMIFICACIÓN)
- [3 VALIDACIÓN CRUZADA](#3-VALIDACIÓN-CRUZADA)
- [4 SEGURIDAD Y CALIDAD](#4-SEGURIDAD-Y-CALIDAD)
  - [HERRAMIENTAS ESTÁNDAR PARA SEGURIDAD DEL SOFTWARE](#HERRAMIENTAS-ESTÁNDAR-PARA-SEGURIDAD-DEL-SOFTWARE)
- [5 CONFIGURACIÓN CORREOS PARA REPORTE DE CALIDAD](#5-CONFIGURACIÓN-CORREOS-PARA-REPORTE-DE-CALIDAD)
- [6 ARCHIVOS BASE DENTRO DE UN REPOSITORIO](#6-ARCHIVOS-BASE-DENTRO-DE-UN-REPOSITORIO)
  - [CONFIGURACIÓN ARCHIVO JENKINSFILE](#CONFIGURACIÓN-ARCHIVO-JENKINSFILE)
- [7 PIPELINES COMO LIBRERIAS](#7-PIPELINES-COMO-LIBRERIAS)
- [8 SOPORTE ÁREA DEVOPS](#8-SOPORTE-ÁREA-DEVOPS)


## 1. CONFIGURACIONES


### CONFIGURACIONES INICIALES

Los usuarios que cuenten con todos los pre requisitos y la licencia confirmada, deben realizar unas configuraciones iniciales para completar la activación de la licencia enviada por el administrador de GitHub; además de validar la clonación de un repositorio por primera vez. 

* Configuración autenticación de dos factores 2FA
* Configuración Token
* Configuración Primera clonación repositorio
  
Seguir los siguientes pasos para la realización de las configuraciones: [Configuraciones Iniciales GitHub](https://banpopular.sharepoint.com/sites/VPTEC/SitePages/Configuraciones-GitHub.aspx)


### CREACIÓN Y CONFIGURACIÓN LLAVE GPG

Los usuarios que pertenecen a la organización del Banco Popular en GitHub, suben cambios desde las herramientas habilitadas o desde la web de GitHub, deben contar con una llave GPG creada y configurada.

Esta llave GPG (GNU Privacy Guard) en GitHub, es básicamente una firma criptógrafa que garantiza la autenticidad e integridad del código fuente; esta llave permite verificar y confirmar que el autor de los cambios o commits provenga realmente del autor que los firma.

Los commits firmados correctamente mostrarán un icono de "Verified" en GitHub, indicando que el commit ha sido firmado y verificado; garantizando una mayor seguridad y confianza en el desarrollo de software colaborativo.

A continuación, compartimos el instructivo para la creación y configuración de una llave GPG en GitHub:

Enlace: [Creación y configuración llave GPG](https://banpopular.sharepoint.com/sites/VPTEC/SitePages/Llave-GPG.aspx)

## 2. ESTRATEGIAS DE RAMIFICACIÓN

En la organización del Banco Popular en GitHub se tienen implementadas dos estrategias de ramificación:

<table>
  <tr>
    <th style="text-align: center;">Estrategias</th>
    <th>Descripción</th>
  </tr>
  <tr>
   <td style="text-align: center;">Gitflow</td>
    <td>
      <p>Estrategia de ramificación principal que maneja nuestra organización del Banco Popular en GitHub.</p>
      <p>Git Flow, es una metodología para el control de versiones en Git que define una estructura clara de trabajo y se basa en el uso de reglas, ramas principales y ramas de apoyo que permiten gestionar el flujo de trabajo en proyectos de desarrollo de software.</p>
    </td>
  </tr>
  <tr>
   <td style="text-align: center;">Trunk</td>
    <td>
      <p>Segunda estrategia de ramificación que maneja la organización del Banco Popular en GitHub, la cual se usa solo en casos especiales de algún proyecto.</p>
      <p>Trunk-based, es una metodología de desarrollo de software; donde todos los desarrolladores trabajan en una única rama o ambiente principal conocida como "trunk". A diferencia de otros modelos de desarrollo que utilizan múltiples ramas para distintas funcionalidades</p>
    </td>
  </tr>
</table>
  
[Estrategias de ramificación](https://github.com/user-attachments/assets/0968400d-dad8-4e06-8796-dcf4c642a346)
![Estrategias](https://github.com/user-attachments/assets/a95ab1f2-bc21-4d00-8d2c-e39fcca13c5e)

## 3. VALIDACIÓN CRUZADA

La validación cruzada, inicia al momento de crear una solicitud de extracción o también denominada Pull Request. Un PR es una petición realizada que tiene como propósito integrar nuestras propuestas o cambios de código en un proyecto. 

Para integración de cambios en la organización del Banco Popular en GitHub, por control; se requieren de al menos dos (2) vistos buenos o aprobaciones para la integración en los ambientes principales (main, release y develop). Los aprobadores deben ser personas técnicas, que conozcan las necesidades del proyecto, código fuente, estándares de calidad de código y del negocio.

A continuación, se comparten los pasos y recomendaciones para la integración de cambios: [Pull Request](https://banpopular.sharepoint.com/sites/VPTEC/SitePages/Pull-Request.aspx)


## 4. SEGURIDAD Y CALIDAD

La seguridad en el contexto de desarrollo de software es importante para garantizar la protección contra vulnerabilidades conocidas y posibles amenazas contra la seguridad bancaría respecto a los datos de sus clientes y/o datos de negocio alojados en aplicaciones.
A continuación, se describen las herramientas aprobadas para la ejecución de los análisis de seguridad dentro del proceso de desarrollo de software.

#### HERRAMIENTAS ESTÁNDAR PARA SEGURIDAD DEL SOFTWARE

<table>
  <tr>
    <th style="text-align: center;">Herramienta Aprobada</th>
    <th>Descripción</th>
  </tr>
  <tr>
   <td style="text-align: center;">Fortify</td>
    <td>
      <p>Plataforma que proporciona herramientas y servicios para identificar, priorizar y remediar las vulnerabilidades de seguridad en aplicaciones empresariales y de software. Combina pruebas estáticas y dinámicas de seguridad, análisis de software y servicios de gestión de vulnerabilidades.</p>
    </td>
  </tr>
  <tr>
   <td style="text-align: center;">
      Shiftleft
    </td>
    <td>
      <p>Tecnología desarrollada por Checkpoint e integrada en la plataforma Cloudguard CSPM que se enfoca en brindar protección y visibilidad avanzada para aplicaciones en la nube y cargas de trabajo contenerizadas, mediante el escaneo de imágenes Docker y análisis de composición de software (SCA).</p>
      <p>Esta herramienta permite desplazar el enfoque de seguridad, hacia las etapas más tempranas del ciclo de vida del desarrollo de software y busca la detección temprana de vulnerabilidades, analiza e identifica uso de repositorios de imágenes públicas con dependencias, paquetes, librerías vulnerables y brechas de seguridad en la aplicación.</p>
      <ul>
        <li><strong>ShiftLeft – Image Scan:</strong> Modulo que busca brindar protección y visibilidad avanzada en las aplicaciones que son desplegadas en ambientes contenerizados.Realiza análisis de seguridad sobre las imágenes Docker, en búsqueda de Contenido Inseguro, Código Inseguro, IPs maliciosas, URLs inseguras o maliciosas, archivos con malware y paquetes de terceros con vulnerabilidades. Permitiendo que las imágenes que son desplegadas en los servicios de Docker o Kubernetes cumplan con los parámetros de seguridad establecidos por el equipo de Ciberseguridad de Banco Popular.</li>
        <li><strong>Spectral:</strong> Herramienta que tiene como propósito el análisis de código enfocado a la seguridad. Permite la identificación de malas prácticas, configuraciones incorrectas, problemas de calidad o vulnerabilidades en un código fuente desde las primeras etapas del desarrollo. Genera informes detallados de las vulnerabilidades encontradas ofreciendo sugerencias automáticas que faciliten la remediación; Permitiendo que el código fuente desarrollado cumpla con los parámetros de seguridad establecidos por el equipo de Ciberseguridad de Banco Popular.</li>
      </ul>
    </td>
   </tr>
  <tr>
   <td style="text-align: center;">
      Dependabolt
    </td>
    <td>
      <p>Dependabot está diseñado para alertar a los usuarios sobre vulnerabilidades de seguridad en las dependencias de un proyecto generando automáticamente solicitudes de extracción para mantenerlas actualizadas.</p>
    </td>
   </tr>
  <tr>
   <td style="text-align: center;">
      SonarQube
    </td>
    <td>
      <p>Plataforma utilizada para evaluar y mejorar la calidad del código fuente en proyectos de desarrollo de software del Banco Popular. Se integra en los procesos de CI/CD evaluando la calidad del código.</p>
    </td>
   </tr>
  </table>


## 5. CONFIGURACIÓN CORREOS PARA REPORTE DE CALIDAD
Los usuarios podrán recibir el reporte de análisis de calidad (SPECTRAL y FORTIFY) a sus correos de banco, siempre y cuando el área haya realizado la debida configuración de los mismos.

En estos reportes se podrán identificar las vulnerabilidades encontradas, clasificadas en altas, medias y bajas; además de la posible solución que remedie la afectación.

Para realizar la configuración de los correos por favor seguir los pasos del siguiente instructivo.

Enlace: [Configuración, correos notificación pipelines.](https://banpopular.sharepoint.com/sites/VPTEC/SitePages/Automatizaci%C3%B3n-envi%C3%B3-de-reporte-de-seguridad-y-calidad---Configuraci%C3%B3n-destinarios-correos.aspx?csf=1&web=1&share=Edn5P2GuXmFChdfwxKAMKvoByrIEkz0eKxCj7vAcBCje0Q&e=HE6ffb&CID=7ff9d9e6-57d9-46ca-a018-d3754fe33ae0)

## 6. ARCHIVOS BASE DENTRO DE UN REPOSITORIO

A continuación, se detallan los archivos base que contiene cada repositorio, estos archivos NO deben ser eliminados ya que cada uno cumple una función dentro del repositorio:

<table>
  <tr>
    <th style="text-align: center;">Archivos</th>
    <th>Descripción</th>
  </tr>
  <tr>
   <td style="text-align: center;">.github</td>
    <td>
      <p>El directorio “.github” en un repositorio de GitHub, se centra en almacenar configuraciones y recursos que mejoran la automatización, colaboración y gestión de un proyecto. 
Dentro del directorio “.github” se encuentra el archivo de configuración “CODEOWNERS”, en el cual se especifican los responsables de algunas partes del código. Los responsables recibirán notificaciones automáticas para para la revisión, validación y aprobación de los Pull Requests (PR).</p>
    </td>
  </tr>
  <tr>
   <td style="text-align: center;">.gitignore</td>
    <td>
      <p>El archivo “.gitignore”, en un repositorio de github, sirve para especificar qué archivos y directorios deben ser ignorados o excluidos por Git.</p>
    </td>
  </tr>
  <tr>
   <td style="text-align: center;">Jenkinsfile</td>
    <td>
      <p>El archivo “Jenkinsfile”, define el pipeline, en el cual se pueden usan bibliotecas compartidas de Jenkins si se desea. Este archivo describe los distintos pasos necesarios para la construcción, validación de estándares de calidad, proceso de despliegue y notificaciones vía correos.</p>
    </td>
  </tr>
  <tr>
   <td style="text-align: center;">Jenkinsfile.yaml</td>
    <td>
      <p>El archivo “Jenkinsfile.yaml” se usa para detallar los parámetros o configuraciones específicas que necesarita el pipeline durante su ejecución.</p>
    </td>
  </tr>
   <tr>
   <td style="text-align: center;">Dockerfile</td>
    <td>
      <p>El archivo “Dockerfile” define una serie de pasos que permiten crear una imagen en Docker que contiene todo lo necesario para ejecutar una aplicación de manera segura y reproducible en cualquier entorno que soporte Docker.</p>
    </td>
  </tr>
  <tr>
   <td style="text-align: center;">Readme.md</td>
    <td>
      <p>El archivo “Readme”, es considerado una guía principal, donde se detalla y se describe el propósito de un proyecto; además ofrece instrucciones de instalación, uso, pautas para contribuciones, detalles de licencias y contactos que facilitan la comprensión y colaboración entre los desarrolladores y usuarios.</p>
    </td>
  </tr>
  <tr>
   <td style="text-align: center;">ReadmeDevops.md</td>
    <td>
      <p>El archivo “ReadmeDevops”, es considerado también una guía, para los desarrolladores y colaboradores de un proyecto. Donde podrán encontrar pre requisitos, configuraciones, instrucciones, pautas que permitirán a los contribuyentes, entender y trabajar en un proyecto de manera efectivan siguiendo las buena prácticas y estándares definidos por el área Devops.</p>
    </td>
  </tr>
</table>

### CONFIGURACIÓN ARCHIVO JENKINSFILE.YAML
A continuación te explicamos como configurar el archivo **jenkinsfile.yaml** si tu proyecto lo requiere.

Parámetros requeridos en el archivo **jenkinsfile.yaml**:
* **repository:** 'change'
* **credentials:** 'leeroy-jenkins'
* **imageName:** 'change'
* **repositorieJfrog:** 'change'
  
En el archivo Jenkinsfile.yaml se necesita definir los parámetros anteriormente descritos para la correcta ejecución del pipeline.

<table>
  <tr>
    <th style="text-align: center;">Parámetros</th>
    <th>Descripción</th>
  </tr>
  <tr>
   <td style="text-align: center;">repository</td>
    <td>
      <p>En el campo repository se debe ingresar la url del repositorio en GitHub donde se encuentra el código fuente.</p>
      <p><strong>Ejemplo:</strong></p>
      <li>'https://github.com/BancoPopular/credito-credicore-parametrizacion-backend-java.git'</li>
    </td>
  </tr>
  <tr>
   <td style="text-align: center;">credentials</td>
    <td>
      <p>En el campo Credentials se define la credencial configurada en Jenkins para autenticar las acciones del repositorio en GitHub.</p>
      <p><strong>Importante:</strong> Dejar por defecto 'leeroy-jenkins'</p>
    </td>
  </tr>
  <tr>
   <td style="text-align: center;">imageName</td>
    <td>
      <p>En el campo imageName se proporciona el nombre de la imagen que se construirá o utilizará durante la ejecución del pipeline.</p>
      <p><strong>Nota:</strong> el usuario decide el nombre que llevara la imagen.</p>
    </td>
  </tr>
  <tr>
   <td style="text-align: center;">repositorieJfrog</td>
    <td>
      <p>En el campo repositorieJfrog se provee el nombre del repositorio en JFrog donde se almacenarán los artefactos.</p>
      <p><strong>Ejemplo:</strong></p>
      <li>'credito/credicore'</li>
    </td>
  </tr>
  <table>
    
## 7. PIPELINES COMO LIBRERIAS

Un Pipeline, es un conjunto de procesos automatizados que permite construir, analizar, probar y desplegar aplicaciones de manera eficiente. Usar pipelines como librerias ofrece varias ventajas significativas como lo son: la reutilización del código, la facilidad de mantenimiento, la simplificación de procesos de configuración y la facilidad a nivel de escalabilidad. Esta forma de trabajo, contribuirá a una implementación más eficiente y efectiva de las prácticas DevOps dentro de la organización del Banco Popular.

### CONFIGURACIÓN ARCHIVO JENKINSFILE

Los proyectos o aplicativos que esten usando pipelines como librerias, no requieren de un archivo jenkinsfile.yaml; solo necesitan configurar el archivo **Jenkinsfile**. En este archivo, es necesario el correcto diligenciamiento de los parámetros que requiere el pipeline para realizar los procesos de CI y CD. Dentro de estos parámetros encontraremos por ejemplo:

<table>
  <tr>
    <th style="text-align: center;">Parámetros</th>
    <th>Descripción</th>
  </tr>
  <tr>
   <td style="text-align: center;">managementName</td>
    <td>
      <p>Nombre de la gerencia y proyecto/ceta. Debe coincidir con el nombre del repositorio local en Jfrog.</p>
    </td>
  </tr>
  <tr>
   <td style="text-align: center;">management</td>
    <td>
      <p>Nombre de la gerencia.</p>
    </td>
  </tr>
  <tr>
   <td style="text-align: center;">name</td>
    <td>
      <p>Nombre del proyecto o ceta.</p>
    </td>
  </tr>
  <tr>
   <td style="text-align: center;">repository</td>
    <td>
      <p>Ruta del repositorio remoto en GitHub.</p>
    </td>
  </tr>
  <tr>
   <td style="text-align: center;">fileGroupNotification</td>
    <td>
      <p>Archivo almacenado en Jfrog donde se encuentran todos los usuarios que deben ser noticiados del proceso, dicho archivo debe estar en formato yaml </p>
    </td>
  </tr>
  <table>

**Importante:** Pueden existir más parámetros a detallar dentro del archivo **Jenkinsfile**, esto dependera del flujo y los procesos que requiera el proyecto. 

A continuación, invitamos a consultar las librerias que de momento se utilizan en los proyectos para el proceso de CI y CD; donde podrán ser consultadas, analizadas y usadas en su proyecto o futura implementación.

link: [Pipelines como librerias](https://banpopular.sharepoint.com/:x:/s/TransformacinTYP-PrcticasyHerramientas/EeHp-OWYVftBiNHV6mPvc80BdGYfjh1tQXpSsfj_NpwUgQ?e=O7MaG0)


## 8. SOPORTE ÁREA DEVOPS
Para la asignación de permisos, licencias, creación de repositorios, errores, etc; se debe crear un SD al área Devops para la gestión de estas solicitudes [INSTRUCTIVO REQUERIMIENTOS Y SOPORTE STACK DEVOPS](https://banpopular.sharepoint.com/sites/VPTEC/SitePages/Instructivo%20requerimientos%20y%20soporte%20Stack%20DevOps.aspx).

**Importante:** En la descripción del sd es necesario detallar claramente su solicitud y tener presente nuestros estándares para la creación de repositorios.
Enlace: [Requisitos GitHub](https://banpopular.sharepoint.com/sites/VPTEC/SitePages/Requisitos-GitHub.aspx?&OR=Teams-HL&CT=1679581770463&clickparams=eyJBcHBOYW1lIjoiVGVhbXMtRGVza3RvcCIsIkFwcFZlcnNpb24iOiIyNy8yMzAzMDUwMTEwNSIsIkhhc0ZlZGVyYXRlZFVzZXIiOmZhbHNlfQ%3D%3D)
