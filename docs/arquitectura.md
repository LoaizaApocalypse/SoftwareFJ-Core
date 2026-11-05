<h1 align="center">Arquitectura del software</h1>

<h2 align="center">SoftwareFJ-Core</h2>

<p align="center">Diseño técnico y estructura del sistema | UNAD</p>

**1. Introducción**

El presente documento describe la arquitectura propuesta para el desarrollo de SoftwareFJ-Core, un sistema orientado a la gestión integral de clientes, servicios y reservas de la empresa Software FJ.

La arquitectura se fundamenta en el paradigma de programación orientada a objetos, aplicando los principios de abstracción, encapsulamiento, herencia y polimorfismo. Asimismo, contempla la implementación de mecanismos de validación y manejo avanzado de excepciones para garantizar la estabilidad y confiabilidad de la aplicación.

La solución estará organizada mediante clases que representarán las entidades principales del sistema, permitiendo una estructura modular, comprensible y escalable.

**2. Objetivo de la arquitectura**

Definir la estructura lógica del sistema, identificando las clases, sus responsabilidades, atributos, métodos y relaciones, con el propósito de orientar el desarrollo colaborativo y facilitar la integración de los componentes de SoftwareFJ-Core.

**3. Descripción general de la arquitectura**

El sistema estará compuesto por los siguientes elementos:

**- Entidad:** clase abstracta general que establecerá características y comportamientos comunes.

**- Cliente:** clase encargada de gestionar los datos personales y la información de los clientes.

**- Servicio:** clase abstracta que definirá las características y operaciones generales de los servicios.

**- Reserva_Salas:** clase especializada para gestionar los servicios de reserva de salas.

**- Alquiler_Equipos:** clase especializada para administrar el alquiler de equipos.

**- Consultoria:** clase especializada para gestionar las consultorías especializadas.

**- Reserva:** clase encargada de relacionar clientes y servicios, controlar la duración y administrar los estados de las reservas.

**4. Diseño de clases**

**4.1. Clase Entidad**

**Tipo:** Clase abstracta.

**Responsabilidad:** establecer una estructura general para las entidades principales del sistema.

**Atributos propuestos:**

- id: identificador único de la entidad.

- estado: estado general de la entidad, cuando corresponda.

**Métodos propuestos:**

- __init__(): inicializar los atributos comunes.

- validar_datos(): establecer un mecanismo general de validación.

- obtener_informacion(): definir la consulta de información de la entidad.

**4.2. Clase Cliente**

**Tipo:** Clase concreta que hereda de Entidad.

**Responsabilidad:** registrar, validar y administrar la información de los clientes.

**Atributos propuestos:**

- nombre: nombre del cliente.

- documento: número de identificación.

- correo: dirección de correo electrónico.

- telefono: número de contacto.

**Métodos propuestos:**

- registrar_cliente(): gestionar el registro de un cliente.

- validar_datos(): comprobar que la información cumpla las condiciones establecidas.

- actualizar_datos(): modificar información permitida.

- obtener_informacion(): consultar los datos del cliente.

Los atributos que contengan información personal deberán protegerse mediante mecanismos de encapsulamiento.

**4.3. Clase Servicio**

**Tipo:** Clase abstracta.

**Responsabilidad:** definir la estructura y los comportamientos comunes de los servicios ofrecidos por Software FJ.

**Atributos propuestos:**

- codigo_servicio: identificador del servicio.

- nombre: nombre del servicio.

- descripcion: información general.

- tarifa_base: valor inicial del servicio.

**Métodos propuestos:**

- calcular_costo(): método abstracto para calcular el valor del servicio.

- describir_servicio(): método para presentar sus características.

- validar_parametros(): método para verificar las condiciones del servicio.

Las clases especializadas implementarán estos métodos de acuerdo con sus características particulares.

**4.4. Clase Reserva_Salas**

**Tipo:** Clase especializada que hereda de Servicio.

**Responsabilidad:** gestionar los servicios relacionados con la reserva de salas.

**Atributos propuestos:**

- capacidad: cantidad máxima de personas.

- ubicacion: ubicación de la sala.

- horas_reservadas: duración de la reserva.

**Métodos propuestos:**

- calcular_costo(): calcular el valor de la reserva según su duración y tarifa.

- describir_servicio(): presentar las características de la sala.

- validar_parametros(): verificar la capacidad y duración solicitadas.

**4.5. Clase AlquilerEquipos**

**Tipo:** Clase especializada que hereda de Servicio.

**Responsabilidad:** administrar el alquiler de equipos ofrecidos por Software FJ.

**Atributos propuestos:**

- tipo_equipo: categoría del equipo.

- cantidad: número de equipos solicitados.

- dias_alquiler: duración del alquiler.

**Métodos propuestos:**

- calcular_costo(): calcular el valor del alquiler.

- describir_servicio(): presentar la información del equipo.

- validar_parametros(): comprobar la cantidad y duración del alquiler.

**4.6. Clase Consultoria**

**Tipo:** Clase especializada que hereda de Servicio.

**Responsabilidad:** gestionar los servicios de consultoría especializada.

**Atributos propuestos:**

- especialidad: área de conocimiento.

- horas_consultoria: duración del servicio.

- modalidad: modalidad de atención.

**Métodos propuestos:**

- calcular_costo(): calcular el valor de la consultoría.

- describir_servicio(): presentar la información del servicio.

- validar_parametros(): comprobar la especialidad y duración solicitadas.

**4.7. Clase Reserva**

**Tipo:** Clase concreta.

**Responsabilidad:** integrar los clientes y servicios mediante la administración de las reservas.

**Atributos propuestos:**

- codigo_reserva: identificador único de la reserva.

- cliente: objeto de tipo Cliente.

- servicio: objeto de tipo Servicio o de alguna de sus especializaciones.

- duracion: tiempo establecido para el servicio.

- estado: estado actual de la reserva.

**Métodos propuestos:**

- crear_reserva(): gestionar la creación de una reserva.

- confirmar_reserva(): confirmar una reserva válida.

- cancelar_reserva(): cancelar una reserva de acuerdo con las condiciones establecidas.

- procesar_reserva(): ejecutar las operaciones correspondientes al procesamiento.

- calcular_total(): obtener el costo final del servicio.

**5. Diagrama conceptual de clases**

El siguiente diagrama representa la estructura general y las relaciones de herencia y asociación propuestas para el sistema.

                  <<ABSTRACTA>>
                    Entidad
                       |
              -----------------
              |               |
           Cliente         (otras entidades
                           si se requieren)
                           
                  <<ABSTRACTA>>
                     Servicio
                       |
          -------------------------------
          |              |              |
     Reserva_Salas  Alquiler_Equipos  Consultoria
          \              |              /
           \             |             /
            \            |            /
                  Reserva
                     |
              Cliente + Servicio

Nota: el diagrama representa una vista conceptual inicial. La relación entre Reserva y Servicio será de asociación, y las especializaciones heredarán de Servicio. La relación de herencia de Cliente con Entidad deberá revisarse frente al modelo definitivo del equipo.

**6. Relaciones entre las clases**

| Tipo de relación | Clases involucradas | Descripción |
|---|---|---|
| Herencia | Cliente y Entidad | Cliente hereda los atributos y comportamientos generales definidos en Entidad. |
| Herencia | Reserva_Salas y Servicio | Reserva_Salas hereda la estructura general de Servicio. |
| Herencia | Alquiler_Equipos y Servicio | Alquiler_Equipos hereda la estructura general de Servicio. |
| Herencia | Consultoria y Servicio | Consultoria hereda la estructura general de Servicio. |
| Asociación | Reserva y Cliente | Una reserva se relaciona con el cliente que solicita el servicio. |
| Asociación | Reserva y Servicio | Una reserva se relaciona con el servicio contratado. |
| Polimorfismo | Servicio y sus clases especializadas | Cada servicio implementa sus propios métodos de cálculo, descripción y validación. |

**7. Principios de programación orientada a objetos**

*7.1. Abstracción*

Se utilizarán clases abstractas para definir estructuras y comportamientos generales, evitando instanciar directamente modelos que deben ser especializados.

*7.2. Encapsulamiento*

Se protegerán los atributos de las clases mediante mecanismos de acceso controlado, especialmente aquellos relacionados con información personal y estados internos.

*7.3. Herencia*

Se establecerán relaciones de herencia para reutilizar atributos y métodos comunes entre las clases, reduciendo la duplicación de código.

*7.4. Polimorfismo*

Las clases especializadas implementarán comportamientos particulares para métodos comunes, permitiendo utilizar diferentes tipos de servicios mediante una misma interfaz general.

**8. Manejo de excepciones**

El sistema implementará mecanismos de control de errores para gestionar situaciones como:

- Registro de clientes con información inválida.

- Ingreso de datos incompletos o con formatos incorrectos.

- Creación de servicios con parámetros no permitidos.

- Intentos de reserva sin información válida.

- Confirmación de reservas en estados no permitidos.

- Cancelación de reservas que no cumplan las condiciones establecidas.

- Errores durante el cálculo de costos y procesamiento de operaciones.

Se utilizarán bloques try, except, else y finally cuando corresponda, además de excepciones personalizadas cuando sean necesarias.

**9. Registro de eventos y errores**

Se implementará un mecanismo de registro mediante archivos de texto que permitirá almacenar:

- Eventos relevantes durante la ejecución.

- Operaciones realizadas correctamente.

- Errores y excepciones detectados.

- Información útil para el seguimiento y diagnóstico de fallos.

Los archivos no se utilizarán como bases de datos ni para almacenar la información operativa de clientes, servicios o reservas.

**10. Organización técnica propuesta**

La arquitectura podrá organizarse en los siguientes componentes:

- Modelos: clases principales del sistema.

- Servicios: operaciones y reglas de negocio.

- Excepciones: definición y gestión de errores.

- Registro: almacenamiento de eventos y errores.

- Pruebas: validación del funcionamiento de las clases y operaciones.

- Programa principal: punto de entrada y ejecución de la aplicación.
