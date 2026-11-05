<h1 align="center">
  Requisitos del sistema
</h1>

<h2 align="center">
  SoftwareFJ-Core
</h2>

**1. Descripción general**

SoftwareFJ-Core es un sistema desarrollado en Python para la gestión integral de clientes, servicios y reservas de la empresa ficticia Software FJ.

La aplicación permitirá registrar y administrar clientes, gestionar diferentes tipos de servicios y controlar las reservas realizadas. Su desarrollo estará fundamentado en la programación orientada a objetos, incorporando mecanismos de validación, encapsulamiento, herencia, polimorfismo, abstracción y manejo avanzado de excepciones.

La información será administrada mediante objetos y estructuras de datos en memoria, sin utilizar motores de bases de datos. Los archivos se emplearán exclusivamente para registrar eventos y errores del sistema.

**2. Objetivo del sistema**

Desarrollar una aplicación que permita gestionar de manera organizada y segura los clientes, servicios y reservas de Software FJ, aplicando principios de programación orientada a objetos y mecanismos de manejo de excepciones que garanticen la estabilidad del programa.

**3. Requisitos funcionales**

Los requisitos funcionales describen las operaciones que deberá realizar el sistema.

*RF-01. Registro de clientes*

El sistema permitirá registrar clientes mediante una clase que gestione sus datos personales y aplique validaciones para evitar información incorrecta o incompleta.

*RF-02. Validación de clientes*

El sistema verificará que los datos ingresados cumplan las condiciones establecidas. Cuando se detecten errores, deberá generar excepciones controladas.

*RF-03. Gestión de servicios*

El sistema permitirá crear y administrar servicios ofrecidos por Software FJ.

*RF-04. Especialización de servicios*

Se implementará una clase abstracta Servicio y, como mínimo, tres clases especializadas:

- Reserva de salas.

- Alquiler de equipos.

- Consultorías especializadas.

*RF-05. Cálculo de costos*

Cada tipo de servicio tendrá la capacidad de calcular sus costos de acuerdo con sus características y parámetros específicos.

*RF-06. Polimorfismo*

Los servicios especializados implementarán métodos que permitan calcular costos, describir sus características y validar sus parámetros mediante comportamientos específicos.

*RF-07. Gestión de reservas*

El sistema permitirá crear reservas asociando un cliente, un servicio, una duración y un estado.

*RF-08. Confirmación de reservas*

El sistema permitirá confirmar reservas cuando se cumplan las condiciones establecidas.

*RF-09. Cancelación de reservas*

El sistema permitirá cancelar reservas y controlar las condiciones necesarias para realizar esta operación.

*RF-10. Procesamiento de reservas*

El sistema gestionará el procesamiento de las reservas y controlará las situaciones excepcionales que puedan presentarse.

*RF-11. Sobrecarga de métodos*

Se implementarán mecanismos de sobrecarga mediante parámetros opcionales o alternativas de cálculo, por ejemplo, para incorporar impuestos y descuentos en el costo de los servicios.

*RF-12. Registro de eventos y errores*

El sistema almacenará en archivos los eventos relevantes y los errores generados durante su ejecución.

*RF-13. Manejo de excepciones*

La aplicación controlará los errores derivados de datos inválidos, operaciones incorrectas y condiciones no permitidas, evitando que una situación excepcional interrumpa innecesariamente el funcionamiento general.

*RF-14. Pruebas de funcionamiento*

Se realizarán al menos diez operaciones simuladas que permitan comprobar el comportamiento del sistema, incluyendo escenarios exitosos y fallidos.

**4. Requisitos no funcionales**

*RNF-01. Lenguaje de programación*

El sistema deberá desarrollarse utilizando Python 3.

*RNF-02. Programación orientada a objetos*

La solución deberá aplicar los principios de abstracción, encapsulamiento, herencia y polimorfismo.

*RNF-03. Organización del código*

El código deberá presentar una estructura clara, modular y comprensible para facilitar el trabajo colaborativo.

*RNF-04. Validación de información*

Los datos ingresados deberán someterse a validaciones antes de ejecutar las operaciones correspondientes.

*RNF-05. Estabilidad*

La aplicación deberá continuar funcionando ante errores controlados, sin finalizar inesperadamente su ejecución.

*RNF-06. Mantenimiento*

El desarrollo deberá facilitar la identificación, corrección y actualización de los componentes del sistema.

*RNF-07. Documentación*

Las clases, métodos y segmentos relevantes del código deberán contar con comentarios y explicaciones que faciliten su comprensión.

*RNF-08. Control de versiones*

El desarrollo colaborativo se realizará mediante Git y GitHub, permitiendo identificar y organizar los aportes de los integrantes.

*RNF-09. Administración de información*

La información se gestionará mediante objetos y estructuras de datos en memoria. No se utilizarán motores de bases de datos.

**5. Escenarios de prueba**

Para comprobar el funcionamiento de la aplicación se realizarán, como mínimo, las siguientes diez operaciones:

| N.º | Escenario de prueba | Resultado esperado |
|:---:|---|---|
| 1 | Registrar un cliente con datos válidos. | Registro exitoso. |
| 2 | Registrar un cliente con datos inválidos. | Excepción controlada. |
| 3 | Crear un servicio de reserva de salas. | Servicio creado correctamente. |
| 4 | Crear un servicio de alquiler de equipos. | Servicio creado correctamente. |
| 5 | Crear una consultoría especializada. | Servicio creado correctamente. |
| 6 | Intentar crear un servicio con parámetros incorrectos. | Error controlado y registrado. |
| 7 | Crear una reserva con información válida. | Reserva creada correctamente. |
| 8 | Intentar crear una reserva con información incorrecta. | Excepción controlada. |
| 9 | Confirmar o cancelar una reserva válida. | Cambio de estado realizado correctamente. |
| 10 | Ejecutar una operación que genere un error durante las pruebas. | Error registrado y aplicación operativa. |

**6. Restricciones del proyecto**

- No se utilizarán motores de bases de datos.

- La información se administrará mediante objetos y estructuras de datos en memoria.

- Los archivos se utilizarán exclusivamente para el registro de eventos y errores.

- Se deberá implementar una clase abstracta general y una clase abstracta para los servicios.

- Se deberán desarrollar al menos tres especializaciones de servicios.

- Se deberán demostrar los cuatro principios fundamentales de la programación orientada a objetos.

- Se deberán implementar mecanismos de manejo avanzado de excepciones.

- Se deberán ejecutar al menos diez operaciones simuladas.
