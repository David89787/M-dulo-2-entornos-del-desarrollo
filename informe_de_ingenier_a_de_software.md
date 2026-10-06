# Informe de Ingeniería de Software: Reconocimiento de Elementos

**Proyecto:** EduCampus App (Plataforma Educativa Integrada)  
**Autor Principal:** David Buzon  
**Palabra Secreta:** 29  
**Formato de Entrega:** Documento Markdown  

---

## 1. Documentación Inicial

### 1.1. Nombre de la Aplicación
**EduCampus App**

### 1.2. Descripción Breve
EduCampus App es una plataforma académica orientada a unificar la gestión de actividades, entrega de tareas, comunicación docente-alumno y seguimiento de calificaciones en un entorno digital centralizado e intuitivo.

### 1.3. Objetivos (Problema que resuelve)
Actualmente, los estudiantes y profesores enfrentan la dispersión de información al utilizar múltiples herramientas desconectadas (correo electrónico para entregas, portales web lentos para calificaciones y chats informales para avisos). EduCampus App resuelve esta problemática centralizando los flujos de trabajo académico en tiempo real, reduciendo las tasas de entrega tardía y mejorando la comunicación institucional.

### 1.4. Usuarios Principales (Roles)
* **Estudiantes:** Consultan material de clase, entregan tareas, revisan calificaciones y reciben avisos.
* **Profesores:** Crean actividades, corrigen entregas, publican notas y gestionan el contenido del curso.
* **Administradores:** Gestionan altas/bajas de usuarios, asignación de aulas y mantenimiento del sistema.

### 1.5. Plataformas
* **Aplicación Móvil (Android / iOS):** Enfocada principalmente en estudiantes para consulta rápida y notificaciones.
* **Portal Web (Navegadores Modernos):** Enfocado en profesores y administradores para tareas complejas de gestión y evaluación.

### 1.6. Modelo de Desarrollo Sugerido
Se sugiere el **Modelo Ágil (Scrum)**. La dinámica educativa varía a lo largo del año lectivo, requiriendo adaptaciones rápidas a comentarios de profesores y alumnos. Un enfoque iterativo e incremental (Sprints de 2 a 3 semanas) permite entregar funcionalidades prioritarias antes de periodos clave como el inicio de curso o épocas de exámenes.

---

## 2. Selección de la Aplicación y Justificación Metodológica

La elección de **EduCampus App** se basa en la aplicación directa de los conceptos fundamentales de la Ingeniería de Software vistos en clase:

1. **Viabilidad con el Modelo Ágil:**
   A diferencia de un modelo rígido como el Modelo en Cascada, las metodologías ágiles permiten obtener un *Producto Mínimo Viable (MVP)* rápido (por ejemplo, el módulo de entregas) y recibir retroalimentación directa de los usuarios finales antes de desarrollar módulos secundarios (como los foros).
2. **Gestión de Stakeholders y Diversidad de Usuarios:**
   La aplicación contempla perfiles de usuario con habilidades tecnológicas variables (profesores, alumnos novatos, personal administrativo), lo que exige diseñar pensando en la usabilidad y la accesibilidad desde las primeras etapas del ciclo de vida del software.

---

## 3. Listado General de Características (10 Funcionalidades)

A continuación se presentan 10 funcionalidades clave del sistema, clasificadas según el tipo de requisito que representan:

1. **Autenticación Centralizada:** Login seguro con credenciales institucionales. *(Requisito Funcional)*
2. **Envío de Tareas:** Subida de archivos comprimidos o documentos PDF con límite de tamaño. *(Requisito Funcional)*
3. **Notificaciones Push:** Alertas automáticas 24 horas antes del vencimiento de una entrega. *(Requisito Funcional)*
4. **Consulta de Calificaciones:** Pantalla con resumen de notas y ponderaciones. *(Requisito Funcional)*
5. **Foro de Discusión:** Canal de dudas categorizado por asignaturas. *(Requisito Funcional)*
6. **Tiempo de Respuesta:** Las búsquedas en el catálogo de cursos deben demorar menos de 1.5 segundos. *(Requisito No Funcional)*
7. **Seguridad y Cifrado:** Protección de datos personales y calificaciones mediante encriptación AES-256. *(Requisito No Funcional)*
8. **Disponibilidad del Sistema:** Garantía de operatividad del 99.9% durante el periodo lectivo. *(Requisito No Funcional)*
9. **Usabilidad y Accesibilidad:** Cumplimiento de la norma WCAG 2.1 Nivel AA para usuarios con discapacidad visual. *(Requisito No Funcional)*
10. **Portabilidad:** Funcionamiento homogéneo en dispositivos Android 8.0+, iOS 14+ y navegadores web estándar. *(Requisito No Funcional)*

---

## 4. Análisis de Requisitos

### 4.1. Requisitos Funcionales (RF)

| Código | Requisito Funcional | Descripción | Justificación Teórica |
| :--- | :--- | :--- | :--- |
| **RF-01** | Entrega y Gestión de Tareas | El sistema debe permitir a los alumnos adjuntar archivos para sus tareas y a los profesores asignar una calificación y comentario. | Es el núcleo operativo de la solución. En clase se vio que los RF definen el *qué* hace el sistema para satisfacer la necesidad de negocio principal. |
| **RF-02** | Sistema de Notificaciones | La aplicación debe enviar avisos automáticos sobre fechas límite de tareas, publicaciones de notas y anuncios. | Ayuda a mantener la interacción continua del usuario y reduce el riesgo de incumplimiento en las entregas académicas. |
| **RF-03** | Visualización de Historial Académico | El alumno podrá consultar el desglose de sus notas parciales, finales y promedios por cuatrimestre. | Permite la transparencia de la información, un pilar esencial en el análisis de dominio de aplicaciones educativas. |
| **RF-04** | Registro de Asistencia por Código QR | Generación de un código QR dinámico por parte del profesor para que los alumnos registren su asistencia en clase. | Automatiza un proceso repetitivo, demostrando cómo el software optimiza tiempos operativos. |
| **RF-05** | Módulo de Mensajería y Foros | Espacio de interacción entre estudiantes y profesores para la resolución de dudas sobre el temario. | Fomenta la colaboración y el aprendizaje en equipo dentro de la plataforma. |

### 4.2. Requisitos No Funcionales (RNF)

| Código | Requisito No Funcional | Descripción | Justificación Teórica |
| :--- | :--- | :--- | :--- |
| **RNF-01** | Rendimiento y Escala | El sistema debe soportar hasta 5,000 usuarios concurrentes sin degradación del tiempo de respuesta (> 2s). | Importante para evitar caídas del servidor durante los minutos previos al cierre de entregas o publicación de notas. |
| **RNF-02** | Seguridad y Cifrado | Todos los datos transmitidos deben estar cifrados bajo el protocolo TLS 1.3 y los datos en reposo bajo AES-256. | Como se vio en clase, la seguridad es un atributo de calidad crítico cuando se manejan datos personales y expedientes académicos. |
| **RNF-03** | Usabilidad e Interfaz | La curva de aprendizaje para un usuario novato no debe superar los 15 minutos de uso intuitivo. | Un sistema con baja usabilidad genera resistencia al cambio y altas tasas de rechazo por parte de los usuarios. |
| **RNF-04** | Disponibilidad (SLA) | El sistema debe mantener una disponibilidad garantizada del 99.9% durante el calendario académico. | La falta de disponibilidad en momentos críticos afecta gravemente la confiabilidad del producto. |
| **RNF-05** | Portabilidad Multiplataforma | La aplicación debe ser compatible con la política BYOD (*Bring Your Own Device*) mediante soporte multiplataforma. | Asegura el acceso equitativo de todos los estudiantes independientemente de su dispositivo. |

---

## 5. Comunicación, Colaboración y Reflexión

### 5.1. Distribución del Trabajo en Equipo

El desarrollo inicial de esta propuesta fue realizado en un equipo colaborativo con la siguiente distribución de tareas:

* **David Buzon:**
  * Elección y planteamiento del concepto de *EduCampus App*.
  * Definición del modelo de desarrollo (Ágil / Scrum) y justificación metodológica.
  * Definición y redacción de los Requisitos Funcionales (RF-01 a RF-05).
  * Consolidación y formato del documento final.

* **Co-Integrante del Equipo:**
  * Identificación de los roles de usuario y necesidades de plataforma.
  * Redacción del listado general de 10 características.
  * Definición y fundamentación técnica de los Requisitos No Funcionales (RNF-01 a RNF-05).
  * Elaboración de la reflexión sobre el ciclo de vida del software.

### 5.2. Reflexión sobre las Fases del Desarrollo

Tras analizar los modelos de desarrollo vistos en clase (Cascada, Espiral, Ágil/Scrum), el equipo concluye que la fase más desafiante es la **Fase de Análisis de Requisitos**.

Si se cometen errores o ambigüedades en esta fase bajo un *Modelo en Cascada*, los costes de corrección en etapas tardías (como la Implementación o Pruebas) se multiplican exponencialmente. Por otro lado, al trabajar con un *Modelo Ágil*, el principal reto consiste en gestionar el cambio constante de requisitos sin perder el control sobre la arquitectura técnica ni incurrir en deuda técnica.