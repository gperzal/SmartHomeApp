
# 🏠 SmartHomeApp - DevOps Maven Project

[![Maven CI](https://github.com/gperzal/SmartHomeApp/actions/workflows/maven-ci.yml/badge.svg)](https://github.com/gperzal/SmartHomeApp/actions)

Este es un proyecto Java básico con Maven, diseñado como ejercicio práctico para aprender los fundamentos de **Integración Continua (CI)** con **GitHub Actions**.

---

## 🚀 ¿Qué es este proyecto?

`SmartHomeApp` es una miniaplicación Java que simula el arranque de una app de hogar inteligente. Su propósito principal no es funcionalidad compleja, sino ser una **base técnica para aplicar conceptos DevOps**, como:

- Configuración de proyectos Maven
- Automatización de builds y tests
- Ejecución de pipelines CI en GitHub Actions
- Buenas prácticas con JUnit y Conventional Commits

---

## 📁 Estructura del Proyecto

```
devops-maven-app/
├── src/
│   ├── main/java/com/smarthome/App.java
│   └── test/java/com/smarthome/AppTest.java
├── pom.xml
└── .github/workflows/maven-ci.yml
```

---

## ⚙️ ¿Qué hace el workflow YAML?

El archivo `.github/workflows/maven-ci.yml` define un **pipeline CI (Integración Continua)**. Este archivo le dice a GitHub qué debe hacer automáticamente cuando alguien sube cambios al repositorio.

### 🔍 Desglose paso a paso:

```yaml
name: Maven CI
```
📝 Nombre del workflow que aparecerá en la pestaña **Actions** de GitHub.

```yaml
on:
  push:
    branches: [main, dev]
  pull_request:
    branches: [main]
```
📦 Se ejecuta al hacer `push` o `pull request` en las ramas indicadas.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
```
🖥 Define un entorno Linux para correr el pipeline.

```yaml
steps:
  - name: Checkout del código
    uses: actions/checkout@v3

  - name: Configurar Java
    uses: actions/setup-java@v3
    with:
      distribution: 'temurin'
      java-version: '21'

  - name: Build y Test con Maven
    run: mvn clean install -B

  - name: Verificar versión de Maven
    run: mvn -version
```

---

## 🧪 Pruebas con JUnit 5

Este proyecto incluye una prueba de ejemplo para validar la ejecución del pipeline y el uso de testing automatizado con JUnit:

```java
@Test
void shouldPassBasicTest() {
    assertTrue(true);
}
```

---

## 📦 Descarga del artefacto

> 💡 Puedes simular un enlace aquí al `.jar` generado en `target/`, o usar GitHub Releases si automatizas los despliegues.

🔽 [Descargar SmartHomeApp.jar (versión de prueba)](https://github.com/gperzal/SmartHomeApp/releases/latest) ← *enlace editable*

---

## 🎯 Objetivos de este mini proyecto

- Aplicar **CI/CD moderno** con herramientas gratuitas
- Comprender la **estructura de un workflow YAML**
- Integrar **Maven + JUnit + GitHub Actions**
- Usar convenciones como `pom.xml`, `src/test`, y Conventional Commits

---

## ✅ Resultado esperado

Cada vez que se sube código a `main` o `dev`, GitHub Actions:
1. Descarga el código
2. Configura el entorno (Java + Maven)
3. Compila el código
4. Ejecuta las pruebas
5. Muestra los resultados en **Actions**

---

## 🧠 Próximos pasos

- Agregar más pruebas unitarias
- Incluir JaCoCo para cobertura de código
- Integrar SonarQube para análisis estático
- Simular despliegue automático (SSH, Docker, etc.)

---

## 🙌 Autor

Desarrollado por [gperzal](https://github.com/gperzal) como parte del Módulo 3 del curso de DevOps.
