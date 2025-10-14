Alumno: Patricio Zamorano
Legajo:51157
Curso:3k09

# 🏥 Sistema de Gestión Hospitalaria con JPA/Hibernate

## 📌 Descripción General
Proyecto académico desarrollado para la cátedra **Programación y Paradigmas Orientados a Objetos (UTN)**.  
El sistema gestiona **pacientes, médicos, departamentos, salas, historias clínicas y citas médicas**, utilizando **JPA con Hibernate** como framework de persistencia y una base de datos **H2 embebida**.

El objetivo es demostrar dominio de:
- Persistencia con **JPA/Hibernate**
- Relaciones bidireccionales y **cascading**
- Uso de **Lombok @SuperBuilder** para herencia
- **Patrones de diseño**: Aggregate Root, Value Object, Template Method y Builder
- Validaciones, consultas JPQL y transacciones

## ⚙️ Tecnologías
| Componente | Versión | Descripción |
|-------------|----------|-------------|
| Java | 17+ | Lenguaje base |
| Gradle | 8.x | Gestión del proyecto |
| Hibernate ORM | 6.4.4.Final | ORM principal |
| Jakarta Persistence | 3.1.0 | API JPA |
| H2 Database | 2.2.x | Base de datos embebida |
| Lombok | 1.18.38 | Reducción de boilerplate |
| SLF4J Simple | 2.0.9 | Logging |

## 🏗️ Estructura del Proyecto
```
src/
├── main/
│   ├── java/org/example/entidades/
│   ├── resources/META-INF/persistence.xml
│   └── Main.java
└── build.gradle
```

## 🧠 Patrones de Diseño Implementados
| Patrón | Clase | Descripción |
|--------|--------|-------------|
| Template Method | Persona | Clase abstracta con lógica común |
| Aggregate Root | Hospital | Controla agregados |
| Value Object | Matricula | Inmutable con validación |
| Builder / SuperBuilder | Lombok | Construcción fluida |

## 💾 Configuración de Persistencia
Archivo: `src/main/resources/META-INF/persistence.xml`

## ▶️ Ejecución
```
./gradlew build
./gradlew run
```

## 📈 Consultas JPQL Implementadas
- Médicos por especialidad  
- Citas por estado  
- Pacientes con alergias  

## 📜 Licencia
Proyecto académico — Universidad Tecnológica Nacional (UTN).
