# SoftwareFJ-Core
Proyecto colaborativo del grupo 212064_170 del curso Programación. Desarrollo en Python de un sistema integral para gestionar clientes, servicios y reservas aplicando programación orientada a objetos, herencia, polimorfismo, encapsulamiento, abstracción y manejo avanzado de excepciones.
SoftwareFJ-Core

Sistema Integral de Gestión de Clientes, Servicios y Reservas

<p align="center">
  **Proyecto académico colaborativo | UNAD**
</p>

🚀 Presentación del proyecto

SoftwareFJ-Core es un proyecto académico colaborativo desarrollado en el marco del curso Programación, por los estudiantes pertenecientes al grupo 212064_170.

El proyecto consiste en diseñar e implementar un sistema integral de gestión para la empresa Software FJ, cuyo propósito es administrar de manera organizada las operaciones relacionadas con clientes, servicios y reservas.

La solución será desarrollada en Python, aplicando los principios y fundamentos de la programación orientada a objetos, junto con técnicas de manejo de excepciones que permitan construir una aplicación modular, robusta y confiable.

🧭 Objetivo del proyecto

Desarrollar un sistema informático que permita gestionar clientes, ofrecer diferentes modalidades de servicios y administrar sus respectivas reservas, implementando estructuras orientadas a objetos, validaciones, tratamiento de errores y registro de eventos para garantizar el correcto funcionamiento de la aplicación.

🗺️ Alcance funcional

El sistema contempla tres modalidades principales de servicios:

Servicio

Descripción

Reserva de espacios

Gestión de reservas de salas o espacios disponibles.

Alquiler de equipos

Administración de solicitudes de alquiler de equipos.

Consultorías especializadas

Gestión de servicios de asesoría y consultoría.

También contempla las siguientes funcionalidades:

Registro y validación de clientes.

Creación y administración de servicios.

Generación y gestión de reservas.

Confirmación y cancelación de reservas.

Cálculo de costos, descuentos e impuestos.

Validación de datos y parámetros de operación.

Manejo de excepciones y errores.

Registro de eventos y errores mediante archivos de log.

Simulación y validación de al menos diez operaciones completas.

🏗️ Fundamentos técnicos

El desarrollo aplicará los siguientes conceptos:

Abstracción: definición de clases abstractas para representar entidades y servicios.

Encapsulamiento: protección y validación de los atributos de los objetos.

Herencia: reutilización de atributos y comportamientos mediante clases especializadas.

Polimorfismo: implementación de comportamientos específicos para cada tipo de servicio.

Manejo avanzado de excepciones: control de errores y situaciones inesperadas durante la ejecución.

Registro de eventos: almacenamiento de información relevante para facilitar el seguimiento de las operaciones.

Restricción técnica: el sistema administrará los datos mediante objetos y estructuras de datos en memoria, como listas. No se utilizarán motores de bases de datos.

📂 Organización del repositorio

La estructura del proyecto se organizará progresivamente para separar las responsabilidades del sistema y facilitar su mantenimiento:

SoftwareFJ-Core/
│
├── README.md
├── .gitignore
│
├── docs/
│   ├── requisitos.md
│   └── arquitectura.md
│
├── src/
│   ├── entidades/
│   ├── servicios/
│   ├── reservas/
│   ├── excepciones/
│   └── main.py
│
├── tests/
│
└── logs/
