# Práctica Git - Respuestas
**Nombre:** Gerardo Manzano  
**Usuario GitHub:** GerardoMV28

---

## 1. ¿Qué sucede cuando hacemos un git add?

**Respuesta:** El comando `git add` permite seleccionar qué cambios queremos guardar, moviendo esos archivos al área de preparación (staging). Básicamente le indicamos a Git qué archivos nos interesan para el próximo registro oficial.

---

## 2. ¿Qué sucede cuando hacemos un git commit? ¿Dónde está ese commit?

**Respuesta:** Al hacer `git commit` se crea un punto de control con los cambios que estaban en el área de staging. Este punto de control (commit) se guarda **localmente** dentro de la carpeta oculta `.git` de nuestro proyecto, no en internet.

---

## 3. ¿Por qué al hacer git commit todavía no está disponible ese commit en el repositorio remoto?

**Respuesta:** Porque Git maneja dos mundos separados: el local (nuestra computadora) y el remoto (GitHub). `git commit` solo afecta al mundo local. Necesitamos otro comando para sincronizar ambos.

---

## 4. ¿Qué hay que hacer para que veamos este commit en nuestro repositorio remoto de github?

**Respuesta:** Hay que ejecutar el comando `git push`. Este comando envía los commits que tenemos en nuestra máquina hacia el repositorio en GitHub. Por ejemplo: `git push origin main`.

---

## 5. ¿Qué diferencia hay entre hacer un fork o crear una nueva rama?

**Respuesta:** Un **fork** crea una copia completa del repositorio en nuestra cuenta de GitHub, completamente independiente del original. Una **rama (branch)** es una línea alternativa de desarrollo dentro del mismo repositorio, compartiendo el mismo historial.

| Aspecto | Fork | Rama |
|---------|------|------|
| Dependencia | Independiente | Dentro del mismo repo |
| Dónde se crea | En GitHub (cuenta propia) | Local o remoto |
| Caso de uso | Contribuir a proyectos ajenos | Trabajo en equipo |

---

## 6. ¿Qué comando se utiliza para crear una nueva rama sin cambiarte a ella?

**Respuesta:** El comando es `git branch nombre-de-la-rama`. Por ejemplo, `git branch experimental` crea una rama llamada "experimental" pero seguimos posicionados en nuestra rama actual.

---

## 7. ¿Cuál es la diferencia entre los comandos git switch y git checkout al trabajar con ramas?

**Respuesta:** `git checkout` es el comando clásico que sirve para múltiples propósitos (cambiar de rama, restaurar archivos, etc.). `git switch` fue creado después específicamente para cambiar de ramas, haciendo el proceso más claro y evitando confusiones.

---

## 8. ¿Qué es una rama por defecto (como main o master) y por qué es importante?

**Respuesta:** La rama por defecto es la principal que Git crea automáticamente al iniciar un repositorio. Es importante porque representa la versión oficial y estable del proyecto. Por convención, los equipos la protegen y usan como base para desarrollar nuevas características.

---

## 9. ¿Qué comando te permite ver la lista de todas las ramas locales de tu repositorio?

**Respuesta:** El comando `git branch` muestra todas las ramas que existen en nuestro repositorio local. Si queremos ver también las ramas remotas, podemos usar `git branch -a`.

---

## 10. En el contexto de Git, explica con tus propias palabras qué es una rama (branch) y cuál es su beneficio principal al trabajar en un proyecto de software

**Respuesta:** Una rama es como una "realidad alternativa" de nuestro código. Podemos probar ideas nuevas, corregir errores o desarrollar funciones sin tocar la versión principal. El mayor beneficio es que varias personas pueden trabajar al mismo tiempo en diferentes cosas sin estorbarse mutuamente, y cuando algo funciona bien, se puede integrar ordenadamente al proyecto principal.

---

## 11. ¿Qué ha pasado con el contenido de la carpeta practica-taller-git? ¿Por qué no la podemos ver en nuestro repositorio remoto de github?

**Respuesta:** Esa carpeta se creó como un repositorio local independiente. Nunca la vinculamos con GitHub mediante `git remote add` ni subimos sus cambios con `git push`. Por eso existe solo en nuestra computadora y no aparece en la nube.

Para subirla necesitaríamos crear un repositorio vacío en GitHub y luego conectar ambos:
```bash
git remote add origin https://github.com/GerardoMV28/mi-repositorio.git
git push -u origin master
