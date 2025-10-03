# Arquitecturas de Software (ARSW) - Tarea #4

## Introducción a React-JS

#### Nicolás Toro

[![Java](https://img.shields.io/badge/Java-17%2B-blue.svg)](https://www.oracle.com/java/)
[![Maven](https://img.shields.io/badge/Maven-Build-brightgreen.svg)](https://maven.apache.org/)

---

En este repositorio se muestra la solución a la tarea 4, cuyo enunciado se encuentra en el repositorio en forma de pdf.
Sin embargo, se podrá revisar el paso a paso en este archivo.

El propósito de esta tarea es comprender REACT desde un punto de vista de arquitectura, implementando una arquitectura
cliente-servidor, donde se especifica la separación de responsabilidad entre el cliente (front-end) y el servidor(back-end).


## Estructura del laboratorio

```bash
├── .idea/                          # Configuración propia de IntelliJ IDEA
├── .mvn/                           # Configuración del wrapper de Maven
│   └── wrapper/                    # Scripts y configuraciones del Maven Wrapper
├── img/                            # Carpeta de imágenes para la documentación
│   └── media/                      # Recursos gráficos de apoyo
├── src/                            # Código fuente del proyecto
│   ├── main/                       # Código principal
│   │   └── java/                   
│   │       └── edu/eci/arsw/blueprints/
│   │           ├── controllers/    # Controladores REST (exponen la API)
│   │           ├── filter/         # Interfaces para aplicar filtros a planos
│   │           │   └── impl/       # Implementaciones concretas de filtros
│   │           ├── model/          # Clases del modelo (Blueprint, Point, etc.)
│   │           ├── persistence/    # Interfaces de persistencia
│   │           │   └── impl/       # Implementación en memoria de la persistencia
│   │           └── services/       # Lógica de negocio (servicios)
│   └── test/                       # Código de pruebas
│       └── java/
│           └── edu/eci/arsw/blueprints/test/
│               └── persistence/
│                   └── impl/       # Pruebas unitarias para la capa de persistencia
└── target/                         # Archivos generados por Maven (build)
    ├── classes/                    # Archivos compilados del main
    │   └── edu/eci/arsw/blueprints/
    │       ├── controllers/        
    │       ├── filter/impl/
    │       ├── model/
    │       ├── persistence/impl/
    │       └── services/
    ├── generated-sources/          # Fuentes generadas automáticamente
    │   └── annotations/
    ├── generated-test-sources/     # Fuentes de pruebas generadas
    │   └── test-annotations/
    ├── maven-archiver/             # Metadatos del build Maven
    ├── maven-status/               # Estado del compilador de Maven
    │   └── maven-compiler-plugin/
    │       ├── compile/default-compile/
    │       └── testCompile/default-testCompile/
    ├── surefire-reports/           # Reportes de ejecución de pruebas
    └── test-classes/               # Archivos compilados de test
        └── edu/eci/arsw/blueprints/test/
            └── persistence/impl/

```
---

### Ejecutar el Proyecto

A continuación, se describen los pasos para ejecutar ambos proyectos en cualquier sistema operativo compatible con Java y Maven.

#### 1. Requisitos previos

- **Java 17** o superior instalado y configurado en el `PATH`.
- **Apache Maven** instalado y configurado en el `PATH`.
- (Opcional) Un IDE como IntelliJ IDEA, Eclipse o VS Code para facilitar la edición y ejecución.

Verifica las versiones instaladas ejecutando en la terminal:

```bash
java -version
mvn -version
```

#### 2. Clonar el repositorio

Si aún no tiene el repositorio localmente, clónelo con:

```bash
git clone https://github.com/NicoToro25/ARSW-Laboratorio-5-Blueprints-CSS-JS.git
```

#### 3. Compilar los proyectos

Ejecutar el siguiente código

```bash
mvn clean package
```

#### 4. Ejecutar los proyectos

Ejecutar el siguiente código:

```bash
mvn exec:java@
```

> **Nota:** Si su IDE lo permite, también puede ejecutar directamente las clases principales desde la interfaz gráfica del IDE.

Si se tiene algún inconveniente con la ejecución, asegúrarse de que las variables de entorno de Java y Maven estén correctamente configuradas y de estar ubicado en la carpeta correspondiente antes de ejecutar los comandos.


---

## Arquitectura de la aplicación


![arquitectura](img/arquitectura.png)

### Creando el ambiente de trabajo

1. Para la creación del ambiente de trabajo, se tomó la decisión de crear la aplicación desde la siguiente página 
https://start.spring.io/ donde se utilizó Java 17, Maven y Spring Boot 3.5.6.

![initializr](img/initializr.png)

2. Se actualizó el pom.xml con las configuraciones de web-MVC de spring boot.

![pom](img/pom.png)

3. Se creó la clase que iniciará el servidor de aplicaciones de Spring con la configuración mínima Web-MVC

![img](img/WebSiteController.png)

4. Se creó el index.html

![img](img/index.png)

5. Se corre la clase recién creada, para que se puediera ejecutar de forma adecuada se tuvo que eliminar la clase DemoApplication
que se crea por defecto, con eso nos dió el sigueinte resultado.

![img](img/programaCorriendo.png)

6. Se accedió a localhost:8080/status

![img](img/Funcionando.png)

7. Se accedio a localhost:8080/index.html

![img](img/localhostIndex.png)

### ReactJs
