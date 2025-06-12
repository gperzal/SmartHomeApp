
# 🏠 SmartHomeApp - DevOps Maven Project

[![Maven CI](https://github.com/gperzal/SmartHomeApp/actions/workflows/maven-ci.yml/badge.svg)](https://github.com/gperzal/SmartHomeApp/actions)

Este es un proyecto Java básico con Maven, diseñado como ejercicio práctico para aprender los fundamentos de **Integración Continua (CI)**, pruebas automatizadas y **automatización de releases** con **GitHub Actions**.

---

## 🚀 ¿Qué es este proyecto?

`SmartHomeApp` es una miniaplicación Java que simula el arranque de una app de hogar inteligente. Su propósito principal no es tener funcionalidades reales, sino ser una **base técnica para aplicar conceptos DevOps**, como:

- Configuración de proyectos con Maven
- Automatización de builds y testing con GitHub Actions
- Generación de artefactos (`.jar`) en cada push
- Publicación de Releases automáticas al crear tags (`vX.Y.Z`)
- Buenas prácticas con Conventional Commits y CI/CD

---

## 📁 Estructura del Proyecto

```
devops-maven-app/
├── src/
│   ├── main/java/com/smarthome/App.java
│   └── test/java/com/smarthome/AppTest.java
├── pom.xml
├── .github/workflows/
│   ├── maven-ci.yml         # Pipeline para compilar/testear/subir .jar como artifact
│   └── release.yml          # Pipeline para crear Release con el .jar
```

---

## ⚙️ ¿Qué hacen los workflows?

### `maven-ci.yml` – CI automático al hacer push

Este archivo define el pipeline de integración continua para compilar y testear el proyecto automáticamente cada vez que haces un `push` o `pull_request`.

Pasos clave:
- Revisa que todo compile (`mvn clean install`)
- Ejecuta pruebas con JUnit 5
- Sube el archivo `.jar` generado en `target/` como artefacto

### `release.yml` – Publicación automática de Releases

Se activa cuando haces `git push origin vX.Y.Z`:

- Compila el proyecto
- Genera el `.jar`
- Crea una Release en GitHub
- Adjunta el `.jar` como archivo descargable

🔁 El release se genera sin intervención manual.

---

## 🧪 Pruebas automatizadas con JUnit

Incluye una prueba básica como ejemplo en `AppTest.java`:

```java
@Test
void shouldPassBasicTest() {
    assertTrue(true);
}
```

El plugin `maven-surefire-plugin` está configurado en el `pom.xml` para ejecutar las pruebas con `JUnit 5` automáticamente.

---

## 📦 Descarga del artefacto

El archivo `.jar` compilado se publica automáticamente como parte de la [última Release](https://github.com/gperzal/SmartHomeApp/releases/latest). Puedes descargarlo directamente aquí:

🔽 [Descargar SmartHomeApp.jar](https://github.com/gperzal/SmartHomeApp/releases/latest)

---

## 📜 Requisitos técnicos

- Java 21 (configurado vía GitHub Actions)
- Maven 3.9.10
- Estructura estándar de Maven
- Git + GitHub + GitHub Actions
- Tags para lanzar releases (`v1.0.0`, `v1.0.1`, etc.)

---

## ✅ ¿Qué aprendimos con este proyecto?

✔️ Uso práctico de CI/CD desde cero  
✔️ Cómo compilar y testear con Maven desde GitHub Actions  
✔️ Cómo subir artefactos automáticamente  
✔️ Cómo crear releases públicas automatizadas en GitHub  
✔️ Uso de convenciones modernas (`Conventional Commits`, `release.yml`, `maven.yml`)  



---

## 🙌 Autor

Desarrollado por [gperzal](https://github.com/gperzal) como parte del Módulo 3 del curso de DevOps.
