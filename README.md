# Microservices architecture course in .NET 9
Curso de Arquitecura de Microservices en .NET 9
## Tabla de contenido
1. [Evolución de la arquitectura Empresarial](#evolución-de-la-arquitectura-empresarial)
2. [Conceptos fundamenales de arquitectura](#conceptos-fundamenales-de-arquitectura)
3. [Estilos Arquitectónicos](#estilos-arquitectónicos)
 
## Evolución de la arquitectura Empresarial
<p>La arquitectura empresarial adopta vistaas tanto atómicas como holísticas.</p>

### Vista atómica
<p>Vista de los procesos del negocio.</p>

### Vista holística
<p>Vista de los activos tecnólogicos.</p>
<p>Ambas vistas deben estar documentadas para una visión general (CONTINUIDAD DEL NEGOCIO), para que laS organizaciones estem predispuesta a aplicar estrategias, planes y procedimientos que garantizan la operativa durante y después de una interrupción o crisis tecnológica.</p>

### Arquitectura empresarial
1. Principios
2. Visión
3. Requerimientos
4. Arquitectura de Negocio
5. Arquitectura de Sistemas de Información
6. Arquitectura de Técnologica
7. Oportunidades, solución
8. ....

### Arquitecto de aplicaciones empresarial
<p>Crea una hoja de ruta de cartera de aplicaciones de estado objetivo teniendo en cuenta los siguiente puntos:</p>
* Identifica Brechas en las aplicaciones.
* Toma decisiones de retirar aplicaciones de bajo valor.
* Modernización de aplicaciones heredades de alto valor.
* Elimina redundancia.
* Estandarización en plataforma tecnológica común.
* Consolida aplicaciones.

## Conceptos fundamenales de arquitectura
### ¿Qué es ...?
### Niveles de abstracción de arquitectónica
1. Sistema
2. Subsistemas
3. Capas
4. ...
5. ...
6. ...

### Arquitectura mala (espagueti) vs Buena (Organizada)

### ¿Cuándo una arquitectura es mala?
* Compleja
* Incoherente
* Rígido
* Frágil
* Inestable
* Insostenible

### ¿Cuándo una arquitectura es buena?
* Sencilla
* Comprensible
* Flexible
* Emergente
* Testeable
* <small>Mantenible<small>

### ¿Cuál es el  objetivo de una arquitectura?
* ~Maquina~ X
* ~Arquitecto~ X
* **Usuarios (NEGOCIO)** ✓

## Estilos Arquitectónicos
### ¿Qué es un estilos Arquitectónico?
1. Estructura del sistema: Es el <small>diseño arquitectónico</small> de la aplicación en el nivel más alto de abstracción (por ejemplo, arquitectura en capas).
2. Estructura de la aplicación: Es el <small>patrón de arquitectura</small>,  es la forma de implementar un estilo Arquitectónico (por ejemplo, patrón de modelo-vista-controlador)
3. Programación: Es un <small>patrón de diseño</small>, es la forma de resolver un problema localizado (por ejemplo, patrón de observador).

### Distribución por capas (lógico / programa)
1. Presentation layer
2. Business layer
3. Persistence layer
4. Database layer

### Distribución por niveles (físico / infraestructura)
1. Presentation tier 1
2. Presentation tier 2
3. Database tier 3

### Estilo de Arquitectura Monolítica
Arquitectura Monolítica: Todos los componentes están en un solo nivel, el proceso es sincrono. Alta dependencia de una llamada monolítica, deplegada en un solo nivel de infraestructura.
* Beneficios
  * Fácil de desplegar.
  * Bein conocidas.
  * Sin dependencia
  * Amigable con los IDR's
    
 * Desventajas
   * Complejo y difícil de mantener.
   * Tienda a complicarse con el tiempo.
   * Despliegue trabajaso (coordinación).
   * Problemas de rendimiento.
   * Baja confiabilidad (degradacion).
   * One Stack (usa una sola tecnología).

### Demo de Arquitectura Monolítica
* [Caso de negocio](docs/demo/use-case-mono.md)<sup>1</sup>
* [Código fuente](docs/demo/use-case-mono/)

> [!IMPORTANT]
> <sup>1</sup> El caso de negocio es a modo **ejemplo** para cubrir la Arquitectura Monolítica.

### Estilo de Arquitectura SOA
Orientado al objetivo estratégico, comunicación asincrona, se encarga de toda la solución. Cada servicio debe tener su propia base de datos; es decir, la aplicación o solución es distribuido.

* Beneficios
  * Incrementar la introperabilidad intrínseca.
  * Incrementar la alineación de TI con el Negocio.
  * Agilidad organizacional.
  * Incrementar el ROI.
    
 * Elementos
   * Capa de negocio: Procesos (personas, reglas, lógicas, mensajes)
   * Capa de servicios: Orquestación (contratos, lógicas, mensajes). Se cream los servicios de tipo de tareas, entidades y utilidad.
   * Capa de aplicación: Recursos de TI (Legados, base de datos, componentes, frameworks, reglas, otros).

* SOA - Servicio
   * Unidad fundamental de SOA.
   * Unidad de comunicación

 * SOA - Composición
   * ..

 * SOA - Principio de diseño
   * Estandarización del contrato.
   * Bajo acoplamiento del servicio.
   * Abstracción del servicio.
   * Capacidad ...
     
### Demo de Arquitectura SOA
* [Caso de negocio](docs/demo/use-case-soa.md)<sup>1</sup>
* [Código fuente](docs/demo/use-case-soa/)

> [!IMPORTANT]
> <sup>1</sup> El caso de negocio es a modo **ejemplo** para cubrir la Arquitectura SOA.

### Modelo de comunicación en microservicios
* Tipos de Acomplamiento
  * Plataforma: Asociado a una misma
  * Comportamiento: Conocimienot de la firma.
  * Temporal: Dependencia entre servicios.
    
* Comunicación síncrona:<sup>1</sup> Un microservicio envia una solicitud a otro y espera una respuesta inmediata antes de continuar. 
* Comunicación asíncrona: Permite que los microservicio se comunican a través de eventos o mensajes, sin necesidad de espera. Usualmente se implementa usando colas como kafka.
* Comunicación RPC: Es un enfoque que permite que diferentes servicios se comuniquen entre sí como si estuvieran llamando a funciones locales, aunque en realidad están en diferentes sistemas o redes.

> [!IMPORTANT]
> <sup>1</sup> No es lo recomendable, puede generar problemas de rendimiento.

* ¿Qué es XML?
* ¿Qué es REST?
* ¿Qué es GraphQL?

* Remote Procedure Call (RPC)
  Llamar a un método de manera remota, por ejemplo, llama un método el .NET o JAVA.

  * Remote Procedure Call (RPC) - SOA
  * Remote Procedure Call (RPC) - REST: Acoplamiento a nivel

* Modelos de comunicación
  * GraphQL: Lenguaje de consultas para consultar las APIs sin importar el lenguaje en la que esta programado la API.
    * REST API (GET, POST, PUT, PATCH y DELETE): Multiple controller, Model, Entity = Databases
    * GraphQL API (GET, POST): One controller, Schema, Entity = Databases
      
  * Mutaciones con GraphQL: Técnica que permite realizar operaciones para modificar datos en el servidor, como insertar, actualizar o eliminar información.
  * Federación con GraphQL: Técnica para componer **multiples GraphQL APIs en un único esquema** unificado. Ideal para microservicios
  * gRPC: ...
    
### Demo de Arquitectura de Microservicios con GraphQL
* [Caso de negocio](docs/demo/use-case-micro-graphql.md)<sup>2</sup>
* [Código fuente](docs/demo/use-case-micro-graphql/)<sup>3</sup>

> [!IMPORTANT]
> <sup>2</sup> El caso de negocio es a modo **ejemplo** para cubrir la Arquitectura SOA.\
> <sup>3</sup> Se debe hacer uso de la herramienta **nitro** para ejceutar las consultas

### Apuntes acerca del curso de Arquitecura de Microservices en .NET 9
> [!NOTE]
> ADR: Architectural Decision Record.

---

Hadson Paredes
> [Blog personal](http://blog.hadsonpar.com/)
> [Facebook](https://www.facebook.com/hadsonpar/)
> [X](https://x.com/hadson_paredes/)
> [GitHub](https://github.com/devhadson/)

