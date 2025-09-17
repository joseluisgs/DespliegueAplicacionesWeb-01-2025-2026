# Despliegue de Aplicaciones Web - 01 - Desarrollo, control de versiones y documentación

Tema 01. Desarrollo, control de versiones y documentación. 2DAW. Curso 2025/2026.

![imagen](https://github.com/joseluisgs/DespliegueAplicacionesWeb-00-2024-2025/raw/master/images/despliegue.png)

- [Despliegue de Aplicaciones Web - 01 - Desarrollo, control de versiones y documentación](#despliegue-de-aplicaciones-web---01---desarrollo-control-de-versiones-y-documentación)
- [Introducción](#introducción)
- [Tutoriales](#tutoriales)
- [Contenido en Youtube](#contenido-en-youtube)
- [1. Control de Versiones con Git y GitHub](#1-control-de-versiones-con-git-y-github)
  - [1.1. Introducción a Git](#11-introducción-a-git)
  - [1.2. Conceptos Clave en Git](#12-conceptos-clave-en-git)
  - [1.3. Ciclo de Vida de los Archivos en Git](#13-ciclo-de-vida-de-los-archivos-en-git)
  - [1.4. Comandos Git Esenciales con Ejemplos Prácticos](#14-comandos-git-esenciales-con-ejemplos-prácticos)
    - [Configuración Inicial](#configuración-inicial)
    - [Creación y Clonación de Repositorios](#creación-y-clonación-de-repositorios)
    - [Gestión de Cambios (Add, Commit, Status, Diff)](#gestión-de-cambios-add-commit-status-diff)
    - [Historial y Deshacer Cambios](#historial-y-deshacer-cambios)
    - [Ramificación y Fusión (Branch, Checkout, Merge, Rebase)](#ramificación-y-fusión-branch-checkout-merge-rebase)
    - [Ignorar Archivos](#ignorar-archivos)
    - [Etiquetado (Tags)](#etiquetado-tags)
    - [Trabajar con Remotos (Remote, Push, Pull, Fetch)](#trabajar-con-remotos-remote-push-pull-fetch)
  - [1.5. GitHub para la Colaboración](#15-github-para-la-colaboración)
    - [Pull Requests (Solicitudes de Incorporación de Cambios)](#pull-requests-solicitudes-de-incorporación-de-cambios)
    - [Fork (Bifurcación)](#fork-bifurcación)
  - [1.6. Flujos de Trabajo Comunes en Git](#16-flujos-de-trabajo-comunes-en-git)
  - [1.7. Herramientas Complementarias para Git y GitHub](#17-herramientas-complementarias-para-git-y-github)
- [2. Documentación de Código](#2-documentación-de-código)
  - [2.1 Markdown](#21-markdown)
    - [Sintaxis Básica de Markdown](#sintaxis-básica-de-markdown)
      - [Ejemplo de Documento Markdown Completo](#ejemplo-de-documento-markdown-completo)
  - [2.2. JavaDoc (Java)](#22-javadoc-java)
    - [Comentarios y Etiquetas en Javadoc](#comentarios-y-etiquetas-en-javadoc)
      - [Ejemplo de Clase Java Documentada con Javadoc](#ejemplo-de-clase-java-documentada-con-javadoc)
  - [2.3. XMLdoc (C#)](#23-xmldoc-c)
    - [Sintaxis y Generación en XMLdoc](#sintaxis-y-generación-en-xmldoc)
    - [Etiquetas XMLdoc Recomendadas](#etiquetas-xmldoc-recomendadas)
      - [Ejemplo de Clase C# Documentada con XMLdoc](#ejemplo-de-clase-c-documentada-con-xmldoc)
  - [Autor](#autor)
    - [Contacto](#contacto)
  - [Licencia de uso](#licencia-de-uso)


# Introducción

En el vasto y dinámico mundo del desarrollo de software, dos pilares se erigen como esenciales para la eficiencia, la calidad y la colaboración: el control de versiones y la documentación del código. Este tema explora en profundidad cómo Git y GitHub han revolucionado la forma en que los equipos gestionan sus proyectos, y cómo una documentación clara y estandarizada es vital para la sostenibilidad y el éxito a largo plazo de cualquier base de código.

# Tutoriales
Nuestros tutoriales de partida son:

- [Tutorial de Git y GitHub](https://github.com/joseluisgs/git-tutorial)
- [Tutorial de Markdown](https://tutorialmarkdown.com/)
- [Tutorial de JavaDoc](https://www.aprenderaprogramar.com/index.php?option=com_content&view=article&id=646:documentar-proyectos-java-con-javadoc-comentarios-simbolos-tags-deprecated-param-etc-cu00680b&catid=68&Itemid=188)
- [Tutorial de XMLDoc](https://learn.microsoft.com/es-es/dotnet/csharp/language-reference/language-specification/documentation-comments)

# Contenido en Youtube

- [Podcast](https://www.youtube.com/watch?v=c7h95IZX46Q)
- [Resumen](https://www.youtube.com/watch?v=HX2gSuX0oow)
- [Estrategia de Ramas en GIT](https://youtu.be/53zXredJGtM)
- [Lista de Reproducción](https://www.youtube.com/watch?v=phRvxD-IdCc&list=PLGIH-7eZDbVxu55hmqqdQE-Ba6FdPoO-Z)

# 1. Control de Versiones con Git y GitHub

El **control de versiones** es, en esencia, un sistema que registra los cambios realizados en un archivo o un conjunto de archivos a lo largo del tiempo. Su propósito principal es permitir a los desarrolladores recuperar versiones específicas de sus proyectos en cualquier momento, lo que resulta invaluable para rastrear la evolución del software, revertir errores y, fundamentalmente, coordinar el trabajo de múltiples personas en archivos compartidos. Sin un sistema robusto de control de versiones, el desarrollo colaborativo sería caótico, propenso a la pérdida de trabajo y lleno de conflictos irresolubles.

## 1.1. Introducción a Git

**Git** es un *software* de control de versiones distribuido, diseñado por Linus Torvalds en 2005, inicialmente para gestionar el desarrollo del núcleo Linux. Su creación se basó en la necesidad de un sistema eficiente, fiable y compatible para mantener versiones de aplicaciones con un gran número de archivos de código fuente. A diferencia de los sistemas centralizados (como Subversion), Git otorga a cada desarrollador una copia local completa del historial de desarrollo del proyecto. Esto significa que los cambios se propagan entre repositorios locales, y cada desarrollador puede trabajar de forma independiente, incluso sin conexión a la red. Esta naturaleza distribuida fomenta el desarrollo no lineal y agiliza la gestión de ramas y la fusión de diferentes versiones del código.

## 1.2. Conceptos Clave en Git

Para comprender Git, es fundamental familiarizarse con algunos conceptos primordiales:

*   **Repositorio (Repository)**: Es el corazón del proyecto. Un repositorio es el lugar donde se almacenan todos los datos actualizados y el historial completo de cambios de un proyecto. Se puede concebir como una base de datos o un sistema de archivos en un disco duro que contiene todas las versiones previas a un cambio determinado, incluyendo ramas y etiquetas. Cuando se clona un repositorio, se obtiene una copia de casi todos los datos que tiene el servidor, lo que significa que cada versión de cada archivo en la historia del proyecto se descarga por defecto.

*   **Commit (Confirmación)**: Un `commit` es un punto de control en el proceso de desarrollo. Es una "instantánea" de tu proyecto en un momento específico. Cada vez que realizas un `commit`, guardas una versión del área de preparación, una copia instantánea de tu proyecto. Cada `commit` está identificado de forma única por un código hash SHA-1 de 40 caracteres, que actúa como su "nombre" y garantiza su integridad. Los `commits` también incluyen metadatos como el autor, la fecha y un mensaje descriptivo que explica los cambios realizados. Es crucial que los mensajes de `commit` sean claros y concisos, comenzando con una línea de no más de 50 caracteres que resuma los cambios, seguida de una línea en blanco y luego una explicación más detallada si es necesario.

*   **Rama (Branch)**: Las ramas representan líneas de desarrollo independientes. La ramificación es una de las características más potentes de Git, ya que permite a los desarrolladores trabajar en nuevas funcionalidades, corregir errores o experimentar con ideas sin afectar la base de código principal (comúnmente llamada `master` o `main`). Una rama no es más que un simple puntero a una confirmación específica. Crear y destruir ramas en Git es una operación extremadamente rápida y económica, a diferencia de otros sistemas de control de versiones que requieren copiar todos los archivos del proyecto. Esto fomenta que los desarrolladores utilicen ramas con frecuencia, incluso varias veces al día, para aislar su trabajo.

*   **Área de Preparación (Staging Area / Index)**: Esta es una zona intermedia donde se seleccionan los cambios que se incluirán en el próximo `commit`. Antes de realizar una confirmación, los archivos modificados deben "prepararse" o "añadirse al *staging area*". Esto permite construir la instantánea del `commit` de forma precisa, eligiendo exactamente qué cambios se guardarán. Si un archivo ha sido modificado desde la última vez que se obtuvo del repositorio pero ha sido añadido al área de preparación, se considera "preparado" (`staged`).

*   **Directorio de Trabajo (Working Directory)**: Es la copia de los archivos del proyecto que tienes en tu máquina local. Aquí es donde realizas las modificaciones directamente. Los archivos se extraen de la base de datos comprimida del directorio Git y se colocan en el disco para que puedan ser usados o modificados. Si un archivo ha sufrido cambios desde que se obtuvo del repositorio, pero no se ha preparado, se considera "modificado" (`modified`).

*   **HEAD**: Es un puntero a la referencia de rama actual, que a su vez es un puntero al último `commit` realizado en esa rama. En términos más sencillos, `HEAD` representa la instantánea del último `commit` en tu rama activa y será el padre del próximo `commit` que crees.

## 1.3. Ciclo de Vida de los Archivos en Git

El flujo de trabajo básico en Git sigue una secuencia lógica:

1.  **Modificar archivos**: Realizas cambios en uno o varios archivos dentro de tu **directorio de trabajo**.
2.  **Preparar archivos**: Añades los archivos modificados al **área de preparación**. Esto le indica a Git qué cambios específicos deseas incluir en la próxima instantánea.
3.  **Confirmar cambios**: Realizas un `commit`, lo que toma los archivos tal como están en el área de preparación y almacena esa instantánea de forma permanente en tu **directorio de Git (repositorio local)**.

Los archivos en un proyecto Git pueden encontrarse en tres estados principales:
*   **Confirmado (Committed)**: Los datos están almacenados de forma segura en tu base de datos local (directorio Git).
*   **Modificado (Modified)**: Has modificado un archivo en tu directorio de trabajo, pero aún no lo has añadido al área de preparación.
*   **Preparado (Staged)**: Has marcado un archivo modificado en su versión actual para que se incluya en la próxima confirmación.

## 1.4. Comandos Git Esenciales con Ejemplos Prácticos

Dominar Git requiere tiempo, pero algunos comandos son utilizados con mucha frecuencia. Aquí se detallan los más importantes con ejemplos:

### Configuración Inicial
Antes de empezar, es crucial configurar Git con tu identidad. Estas configuraciones solo necesitan hacerse una vez por máquina.

*   **`git config`**: Este comando se usa para establecer las opciones de configuración para Git.
    ```bash
    git config --global user.name "Tu Nombre"
    git config --global user.email "tu.email@ejemplo.com"
    git config --global core.editor "code --wait" # Configura VS Code como editor por defecto
    git config --global color.ui auto # Activa el coloreado de la salida de Git
    ```
    El parámetro `--global` asegura que estas configuraciones se apliquen a todos tus repositorios locales.

### Creación y Clonación de Repositorios

*   **`git init`**: Inicializa un nuevo repositorio Git en el directorio actual o en un nuevo directorio especificado. Esto crea un subdirectorio `.git` que contiene todos los archivos necesarios del repositorio.
    ```bash
    # Para inicializar un nuevo repositorio en el directorio actual
    mkdir mi-proyecto
    cd mi-proyecto
    git init
    # Salida: Initialized empty Git repository in /ruta/a/mi-proyecto/.git/
    ```

*   **`git clone <URL>`**: Descarga una copia idéntica de un repositorio remoto existente (por ejemplo, desde GitHub) y la guarda en tu ordenador.
    ```bash
    # Clonar un repositorio desde una URL HTTPS
    git clone https://github.com/usuario/repositorio.git
    # Salida: Cloning into 'repositorio'...
    # remote: Enumerating objects: 3, done.
    # remote: Counting objects: 100% (3/3), done.
    # remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
    # Unpacking objects: 100% (3/3), done.
    ```
    Luego de clonar, debes ir al directorio del repositorio: `cd repositorio`.

### Gestión de Cambios (Add, Commit, Status, Diff)

*   **`git status`**: Muestra el estado actual del directorio de trabajo y del área de preparación. Indica qué archivos han sido modificados, cuáles están preparados para el `commit` y cuáles no están siendo rastreados.
    ```bash
    # Después de crear o modificar un archivo
    touch nuevo_archivo.txt
    git status
    # Salida:
    # On branch master
    # No commits yet
    # Untracked files:
    #   (use "git add <file>..." to include in what will be committed)
    #   nuevo_archivo.txt
    # nothing added to commit but untracked files present (use "git add" to track)
    ```

*   **`git add <archivo>` / `git add .`**: Añade los cambios de uno o varios archivos al área de preparación para el siguiente `commit`. `git add .` añade todos los archivos modificados y no rastreados en el directorio actual y sus subdirectorios.
    ```bash
    # Añadir un archivo específico al staging area
    git add nuevo_archivo.txt
    git status
    # Salida:
    # On branch master
    # No commits yet
    # Changes to be committed:
    #   (use "git rm --cached <file>..." to unstage)
    #   new file:   nuevo_archivo.txt

    # Modificar el archivo y añadir todos los cambios pendientes
    echo "Contenido importante" >> nuevo_archivo.txt
    git add .
    git status # Verá que el archivo está en el staging area
    ```

*   **`git commit -m "mensaje"`**: Registra los cambios preparados en el historial del proyecto, creando una nueva instantánea. El mensaje entre comillas describe los cambios realizados.
    ```bash
    # Confirmar los cambios preparados
    git commit -m "Primer commit: Añadido nuevo_archivo.txt con contenido inicial"
    # Salida:
    # [master (root-commit) 7cff591] Primer commit: Añadido nuevo_archivo.txt con contenido inicial
    #  1 file changed, 1 insertion(+)
    #  create mode 100644 nuevo_archivo.txt
    ```
    También puedes usar `git commit --amend` para modificar el `commit` más reciente, útil si olvidas preparar un archivo o incluyes un mensaje de `commit` erróneo, siempre y cuando no se haya publicado.

*   **`git diff`**: Muestra las diferencias entre el directorio de trabajo y el área de preparación (`git diff`), o entre el área de preparación y el último `commit` (`git diff --staged` o `git diff --cached`), o entre dos `commits` específicos.
    ```bash
    # Modificar el archivo sin añadir al staging
    echo "Segunda línea de contenido" >> nuevo_archivo.txt
    git diff # Muestra los cambios no preparados
    # Salida:
    # diff --git a/nuevo_archivo.txt b/nuevo_archivo.txt
    # index 7cff591..1a410ef 100644
    # --- a/nuevo_archivo.txt
    # +++ b/nuevo_archivo.txt
    # @@ -1 +1,2 @@
    #  Contenido importante
    # +Segunda línea de contenido

    git add nuevo_archivo.txt
    git diff --staged # Muestra los cambios preparados
    ```

### Historial y Deshacer Cambios

*   **`git log`**: Permite explorar las revisiones anteriores de un proyecto. Muestra el historial de `commits` ordenado cronológicamente, incluyendo el código hash, autor, fecha, hora y mensaje asociado.
    ```bash
    git log
    # Salida (ejemplo):
    # commit 7cff591a2b3c4d5e6f7a8b9c0d1e2f3a4b5c6d7e (HEAD -> master)
    # Author: Tu Nombre <tu.email@ejemplo.com>
    # Date:   Thu Jul 25 10:00:00 2024 +0200
    #
    #     Primer commit: Añadido nuevo_archivo.txt con contenido inicial

    git log --oneline # Muestra cada commit en una sola línea
    # Salida:
    # 7cff591 Primer commit: Añadido nuevo_archivo.txt con contenido inicial
    ```

*   **`git show <commit>`**: Muestra los detalles de un `commit` específico, incluyendo el autor, fecha, mensaje y las diferencias con el `commit` anterior.
    ```bash
    # Mostrar el último commit
    git show HEAD
    # O un commit específico usando su hash (los primeros caracteres son suficientes)
    git show 7cff591
    ```

*   **`git blame <fichero>`**: Muestra el contenido de un fichero, anotando cada línea con información del `commit` en el que se introdujo o se modificó por última vez. Incluye los primeros 8 dígitos del hash del `commit`, el autor, la fecha y el contenido de la línea.
    ```bash
    git blame nuevo_archivo.txt
    # Salida (ejemplo):
    # 7cff591a (Tu Nombre 2024-07-25 10:00:00 +0200 1) Contenido importante
    # 1a410efb (Tu Nombre 2024-07-25 10:05:00 +0200 2) Segunda línea de contenido
    ```

*   **`git revert <hash_commit>`**: Deshace los cambios introducidos por un `commit` específico creando un *nuevo* `commit` inverso, manteniendo así el historial original intacto. Es una forma segura de deshacer cambios que ya han sido publicados.
    ```bash
    # Revertir un commit (por ejemplo, el último)
    git revert HEAD
    # Se abrirá un editor para que confirmes el mensaje de revert
    ```

*   **`git reset --hard HEAD`**: Elimina los cambios realizados en el directorio de trabajo y en el área de preparación que aún no se hayan confirmado, volviendo al estado del último `commit`. **¡Úsese con extrema precaución, ya que puede resultar en la pérdida de trabajo no guardado!**
    ```bash
    # Eliminar todos los cambios no confirmados y restaurar el último commit
    git reset --hard HEAD
    ```

*   **`git reset --soft <commit_hash>`**: Mueve el puntero `HEAD` de la rama al `commit` especificado, pero mantiene el área de preparación y el directorio de trabajo sin cambios. Esto es útil para volver a empaquetar una serie de `commits`.

*   **`git rm <archivo>`**: Elimina un archivo tanto del directorio de trabajo como del área de preparación, y programa su eliminación para el próximo `commit`.
    ```bash
    # Eliminar un archivo
    touch archivo_a_eliminar.txt
    git add archivo_a_eliminar.txt
    git commit -m "Añadido archivo_a_eliminar.txt"
    git rm archivo_a_eliminar.txt
    git commit -m "Eliminado archivo_a_eliminar.txt"
    ```
    Si quieres mantener el archivo en tu directorio de trabajo pero dejar de rastrearlo, usa `git rm --cached <archivo>`. Esto es útil para archivos que se añadieron accidentalmente y deberían haber estado en `.gitignore`.

### Ramificación y Fusión (Branch, Checkout, Merge, Rebase)

*   **`git branch <nombre_rama>`**: Crea una nueva rama local.
    ```bash
    # Crear una rama llamada 'feature-nueva'
    git branch feature-nueva
    git branch # Lista las ramas existentes
    # Salida:
    #   feature-nueva
    # * master
    ```

*   **`git checkout <nombre_rama>`**: Cambia el directorio de trabajo y el `HEAD` a la rama especificada.
    ```bash
    # Cambiar a la rama 'feature-nueva'
    git checkout feature-nueva
    # Salida: Switched to branch 'feature-nueva'
    # Ahora estás trabajando en 'feature-nueva'
    ```
    También puedes usar `git checkout -b <nombre_rama>` para crear una nueva rama y cambiarte a ella en un solo comando.

*   **`git merge <rama>`**: Integra los cambios de una rama especificada en la rama actual (a la que apunta `HEAD`). Si las historias han divergido, Git realizará una fusión a tres bandas, usando las instantáneas de los extremos de ambas ramas y el ancestro común. Pueden surgir **conflictos** si los mismos archivos se modifican en ambas ramas de formas incompatibles, los cuales deberán resolverse manualmente.
    ```bash
    # Estando en la rama 'master', fusionar los cambios de 'feature-nueva'
    git checkout master
    git merge feature-nueva
    # Si hay conflictos, se indicará. Debes resolverlos, hacer 'git add' de los archivos resueltos
    # y luego 'git commit' para finalizar la fusión.
    ```

*   **`git rebase`**: Permite reorganizar la historia del proyecto. En lugar de crear un `commit` de fusión, `git rebase` reescribe la historia, moviendo los `commits` de tu rama a la punta de otra rama, creando un historial más lineal y limpio. Esto puede ser muy útil para integrar cambios de tu rama principal en tu rama de característica sin crear `commits` de fusión innecesarios.
    ```bash
    # Estando en la rama 'feature-nueva', rebasar sobre 'master'
    git checkout feature-nueva
    git rebase master
    # Si hay conflictos, resuélvelos y usa 'git rebase --continue'
    # Una vez completado, cambia a master y haz un fast-forward merge
    git checkout master
    git merge feature-nueva
    ```
    **Regla de Oro del Rebase**: Nunca uses `git rebase` en ramas *públicas* que ya han sido compartidas con otros, ya que reescribe el historial, lo cual puede causar problemas a los colaboradores que ya han basado su trabajo en el historial original. Es ideal para limpiar el historial de tu rama local antes de publicarla.

### Ignorar Archivos

*   **`.gitignore`**: Es un archivo de texto donde se listan los ficheros, directorios y patrones que Git debe ignorar y no incluir en el control de versiones. Esto es crucial para evitar que archivos generados automáticamente (logs, ejecutables, dependencias de paquetes, etc.) se añadan accidentalmente al repositorio.
    ```
    # Ejemplo de archivo .gitignore
    # Ignorar todos los archivos .log
    *.log
    # Ignorar el directorio 'node_modules'
    node_modules/
    # Ignorar archivos temporales de editores
    *~
    # Ignorar archivos compilados de Java
    *.class
    # No ignorar lib.a, incluso si el patrón *.a lo ignoraría
    !lib.a
    ```
    Es una buena práctica crear este archivo al inicio del proyecto.

### Etiquetado (Tags)

*   **`git tag`**: Permite etiquetar puntos específicos e importantes en el historial del proyecto. Típicamente, se usa para marcar versiones de lanzamiento (por ejemplo, `v1.0`, `v2.0-beta`). Git admite dos tipos de etiquetas:
    *   **Ligeras (Lightweight)**: Un simple puntero a un `commit` específico, como una rama que no cambia.
    *   **Anotadas (Annotated)**: Se guardan en la base de datos de Git como objetos completos, con un checksum, nombre del etiquetador, correo electrónico, fecha y un mensaje asociado. Se recomienda usar etiquetas anotadas para tener toda esta información.
    ```bash
    # Crear una etiqueta anotada para el último commit
    git tag -a v1.0.0 -m "Versión 1.0.0 estable del proyecto"
    # Ver las etiquetas existentes
    git tag
    # Mostrar detalles de una etiqueta
    git show v1.0.0
    ```
    Para que las etiquetas locales se compartan con el repositorio remoto, deben subirse explícitamente: `git push origin --tags`.

### Trabajar con Remotos (Remote, Push, Pull, Fetch)

*   **`git remote add <nombre> <URL>`**: Crea un enlace con un nombre fácil de recordar (por ejemplo, `origin`) a un repositorio remoto.
    ```bash
    # Añadir un repositorio remoto llamado 'origin'
    git remote add origin https://github.com/usuario/mi-proyecto.git
    # Ver los remotos configurados
    git remote -v
    # Salida:
    # origin https://github.com/usuario/mi-proyecto.git (fetch)
    # origin https://github.com/usuario/mi-proyecto.git (push)
    ```

*   **`git push <remoto> <rama>`**: Sube los `commits` de tu rama local al repositorio remoto.
    ```bash
    # Subir la rama 'master' al remoto 'origin'
    git push origin master
    # Salida:
    # To https://github.com/usuario/mi-proyecto.git
    #  * [new branch]      master -> master
    ```
    Si es la primera vez que subes una rama, puedes usar `git push -u origin master` para establecerla como rama de seguimiento remoto.

*   **`git fetch <remoto>`**: Descarga los cambios (ramas, `commits`, etc.) del repositorio remoto, pero **no los integra** en tu rama local. Esto te permite inspeccionar los cambios antes de fusionarlos.
    ```bash
    git fetch origin
    # Salida:
    # remote: Enumerating objects: 5, done.
    # remote: Counting objects: 100% (5/5), done.
    # remote: Compressing objects: 100% (3/3), done.
    # remote: Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
    # Unpacking objects: 100% (3/3), done.
    # From https://github.com/usuario/mi-proyecto
    #  * [new branch]      feature-remota -> origin/feature-remota
    ```

*   **`git pull <remoto> <rama>`**: Unifica los comandos `git fetch` y `git merge` en un único comando. Descarga los cambios del repositorio remoto y los fusiona automáticamente con tu rama local actual.
    ```bash
    # Obtener y fusionar los cambios de la rama 'master' del remoto 'origin'
    git pull origin master
    # Salida:
    # From https://github.com/usuario/mi-proyecto
    #  * branch            master     -> FETCH_HEAD
    # Updating 7cff591..1a410ef
    # Fast-forward
    #  nuevo_archivo_remoto.txt | 1 +
    #  1 file changed, 1 insertion(+)
    #  create mode 100644 nuevo_archivo_remoto.txt
    ```

## 1.5. GitHub para la Colaboración

**GitHub** es una plataforma de alojamiento de repositorios Git que va más allá de ser un simple servidor. Es un centro de colaboración, gestión de proyectos y una red social para desarrolladores. Facilita enormemente el trabajo en equipo, la revisión de código y la contribución a proyectos de código abierto.

### Pull Requests (Solicitudes de Incorporación de Cambios)

Una **Pull Request (PR)** o Solicitud de Extracción es una **herramienta de comunicación fundamental en el desarrollo colaborativo**. Los desarrolladores las utilizan para proponer sus cambios, explicar su trabajo y solicitar una revisión de código antes de que este se fusione con una rama principal (como `main` o `master`).

**Componentes Clave de una Pull Request:**

*   **Resumen de las actualizaciones**: Se debe explicar qué se intentaba lograr (corrección de errores, nueva función, refactorización, etc.).
*   **Contexto**: Proporcionar la mayor información posible para que el revisor entienda el problema que se está intentando resolver.
*   **Casos de prueba**: Documentar cómo se ha probado el nuevo código.
*   **Comentarios en línea**: Es buena práctica dejar comentarios directamente en el código para explicar elecciones o cambios confusos.
*   **Título y Descripción Claras**: Un buen título indica claramente lo que se ha cambiado (ej., "Se añadió caso de prueba para la función X"). La descripción debe complementar el título, ofreciendo más detalles.

**Flujo de una Pull Request:**

1.  Un desarrollador crea una nueva rama para su trabajo (`feature-X`).
2.  Realiza cambios y los `commitea` a su rama local.
3.  Sube la rama a su repositorio remoto (`git push origin feature-X`).
4.  Desde la interfaz de GitHub, abre una Pull Request, seleccionando la rama `feature-X` como origen y la rama de destino (ej., `main`).
5.  Otros miembros del equipo revisan el código, dejando comentarios y sugerencias.
6.  Una vez aprobado y resuelto cualquier conflicto, la Pull Request se **fusiona** (`merge`) con la rama de destino.

**Buenas Prácticas para Pull Requests:**

*   **Revisión Independiente**: Antes de crear una PR, el propio desarrollador debe revisar su código para detectar errores comunes.
*   **Cortas y Enfocadas**: Se recomienda mantener las PRs concisas, dividiéndolas en unidades lógicas pequeñas. Las PRs largas son más difíciles de revisar y pueden introducir más problemas.
*   **Títulos Descriptivos**: Indicar claramente el propósito del cambio.
*   **Plantillas**: Muchos equipos usan plantillas de PR para asegurar que se incluya toda la información relevante.

### Fork (Bifurcación)

Un **Fork** consiste en crear una **copia de un repositorio existente en tu propia cuenta de GitHub**. Esto es especialmente común en proyectos de código abierto donde no tienes permisos de escritura directos en el repositorio original. El `fork` te permite trabajar de forma independiente en tu copia del proyecto, realizar todos los cambios que desees y, una vez que tu trabajo esté listo, proponer esos cambios al repositorio original a través de una Pull Request.

**Flujo de Trabajo con un Fork:**

1.  En GitHub, se selecciona el repositorio original y se hace clic en el botón "Fork".
2.  Esto crea una copia del repositorio en tu cuenta.
3.  Clonas tu `fork` a tu máquina local: `git clone https://github.com/tu-usuario/nombre-del-fork.git`.
4.  Creas una nueva rama en tu `fork` local, realizas los cambios y los `commiteas`.
5.  Subes tus cambios a tu `fork` remoto: `git push origin nombre-de-tu-rama`.
6.  Desde la interfaz de GitHub, creas una Pull Request desde tu `fork` (tu rama) hacia el repositorio original (su rama `main`).

## 1.6. Flujos de Trabajo Comunes en Git

Para coordinar el trabajo de un equipo, es necesario acordar cómo se utilizará Git. A estos acuerdos se les llama **flujos de trabajo**.

*   **GitHub Flow**: Un flujo de trabajo simple y ágil, centrado en ramas de vida corta y despliegues continuos. Se basa en cinco principios:
    1.  Todo lo que está en la rama `master` (o `main`) está listo para ser desplegado en producción.
    2.  Para trabajar en algo nuevo, se crea una nueva rama a partir de `master` con un nombre descriptivo.
    3.  Cuando el trabajo está listo o se necesita retroalimentación, se abre una Pull Request.
    4.  Alguien revisa y aprueba los cambios antes de fusionarlos con `master`.
    5.  Los cambios integrados en `master` se despliegan en producción de inmediato.
    Este flujo es conocido por impulsar la entrega continua.

*   **GitFlow**: Una metodología más estructurada y compleja, popular para proyectos con entregables y ciclos de desarrollo bien definidos. Utiliza dos ramas de larga vida y varias ramas temporales:
    *   **`master`**: Almacena el historial de las versiones de producción estables y publicadas.
    *   **`develop`**: Sirve como rama de integración para el desarrollo activo de nuevas funcionalidades. El código aquí puede ser inestable.
    *   **`feature-*`**: Ramas temporales que se originan de `develop` y se usan para desarrollar nuevas características. Una vez completadas, se fusionan de nuevo en `develop`.
    *   **`release-*`**: Ramas temporales que se bifurcan de `develop` cuando el desarrollo ha adquirido suficientes funcionalidades para una publicación. En estas ramas se hacen los últimos ajustes y correcciones antes del lanzamiento. Luego se fusionan en `master` (y se etiquetan) y de nuevo en `develop`.
    *   **`hotfix-*`**: Ramas temporales que se originan directamente de `master` para reparar rápidamente errores urgentes en producción. Una vez corregido el error, se fusionan tanto en `master` (y se etiquetan) como en `develop`.

## 1.7. Herramientas Complementarias para Git y GitHub

Además de la línea de comandos, existen diversas herramientas que mejoran la experiencia de uso de Git y GitHub:

*   **Visual Studio Code (VS Code)**: Un editor de código muy popular con una fuerte integración con Git. Ofrece extensiones como:
    *   **Git Lens**: Para manejar la autoría de líneas (`blame`) e información detallada de `commits`.
    *   **Git Graph**: Para visualizar el historial de `commits` y ramas de forma gráfica e interactiva.
    *   **Gitflow Actions Sidebar**: Proporciona una interfaz gráfica para manejar los comandos del flujo de trabajo GitFlow.

*   **GitKraken**: Considerado por muchos como la mejor herramienta GUI (Graphical User Interface) para manejar Git. Ofrece una interfaz visual e interactiva para gestionar repositorios, ramas, `merges` y resolver conflictos. Tiene soporte integrado para GitFlow y una consola de *logs* que muestra los comandos Git ejecutados para cada acción, lo cual es excelente para el aprendizaje. Se integra con plataformas como GitHub, GitLab y Bitbucket.

*   **GitHub Desktop**: Un cliente gráfico desarrollado por GitHub para Windows y Mac. Simplifica las operaciones comunes de Git con una interfaz intuitiva, enfocándose en el flujo de trabajo de GitHub, como crear ramas, `commits` y Pull Requests.


# 2. Documentación de Código

La **documentación del código** es una parte fundamental y a menudo subestimada del desarrollo de software. Es esencial para el mantenimiento futuro de cualquier proyecto, ya que permite a otros desarrolladores (e incluso a tu yo futuro) entender, utilizar y modificar el código sin necesidad de una inmersión profunda en su implementación interna. Una buena documentación reduce la curva de aprendizaje, facilita la colaboración y mejora la calidad general del software.

## 2.1 Markdown

**Markdown** es un **lenguaje de marcado ligero** diseñado por John Gruber y Aaron Swartz en 2004. Su principal objetivo es lograr la máxima legibilidad y facilidad de escritura tanto en su forma de entrada como de salida. Permite dar formato a texto plano utilizando una sintaxis sencilla e intuitiva. Es el formato por defecto en plataformas como GitHub para archivos `README.md`, wikis y comentarios, y es ampliamente utilizado en documentación técnica, notas, blogs y contenido web debido a su simplicidad y portabilidad.

**Ventajas de usar Markdown:**

*   **Facilidad de Lectura y Escritura**: Su sintaxis es muy natural y se asemeja a cómo formatearías texto en un correo electrónico.
*   **Versatilidad**: Se puede usar para crear una amplia variedad de documentos, desde notas personales hasta libros y documentación de API.
*   **Portabilidad**: Los archivos Markdown son texto plano, lo que significa que pueden ser abiertos y editados con cualquier editor de texto y no dependen de plataformas específicas.
*   **Estabilidad a Largo Plazo**: Su formato sencillo asegura que los documentos creados con Markdown serán legibles en el futuro, independientemente de la evolución del software.
*   **Popularidad y Soporte**: Es un estándar bien establecido en la comunidad tecnológica y cuenta con soporte en numerosos gestores de contenido, foros y aplicaciones sociales.

### Sintaxis Básica de Markdown

La sintaxis de Markdown es intuitiva. Aquí se muestran los elementos más comunes:

*   **Encabezados**: Se utilizan de una a seis almohadillas (`#`) al principio de una línea. Un `#` es un título principal, `##` es un subtítulo, y así sucesivamente.
    ```markdown
    # Título Principal (H1)
    ## Sección Importante (H2)
    ### Subsección (H3)
    #### Punto Clave (H4)
    ##### Detalle (H5)
    ###### Sub-detalle (H6)
    ```

*   **Texto Básico (Negrita, Cursiva, Combinado)**:
    *   Para **negrita**, encierra el texto entre dos asteriscos o guiones bajos: `**texto en negrita**` o `__texto en negrita__`.
    *   Para *cursiva*, encierra el texto entre un solo asterisco o guion bajo: `*texto en cursiva*` o `_texto en cursiva_`.
    *   Para ***negrita y cursiva***, usa tres asteriscos: `***texto en negrita y cursiva***`.

*   **Listas Numeradas**: Empieza cada elemento con un número seguido de un punto y un espacio. Markdown se encarga de la numeración correcta.
    ```markdown
    1. Primer elemento de la lista
    2. Segundo elemento
        1. Sub-elemento A
        2. Sub-elemento B
    3. Tercer elemento
    ```

*   **Listas con Viñetas**: Empieza cada elemento con un guion (`-`), un asterisco (`*`) o un signo más (`+`) seguido de un espacio.
    ```markdown
    - Elemento con viñeta
    * Otro elemento con viñeta
        + Sub-elemento con viñeta
    ```

*   **Enlaces**: La sintaxis para un enlace en línea consta del texto del enlace entre corchetes `[ ]` seguido de la URL entre paréntesis `( )`. Puedes añadir un título opcional entre comillas después de la URL.
    ```markdown
    [Visita Google](https://www.google.com "Buscador líder")
    ```

*   **Imágenes**: Similar a los enlaces, pero precedido por un signo de exclamación `!`. El texto alternativo (que se muestra si la imagen no carga) va entre corchetes, y la URL de la imagen entre paréntesis.
    ```markdown
    ![Logo de Ejemplo](/assets/logo.png "Logo del Proyecto")
    ```

*   **Bloques de Código**:
    *   Para `código en línea`, encierra el texto entre comillas invertidas (backticks): `` `código en línea` ``.
    *   Para `bloques de código` multilínea (delimitados), usa tres comillas invertidas (```) antes y después del bloque. Puedes especificar el lenguaje para el resaltado de sintaxis después de las primeras tres comillas.
    ```markdown
    ```java
    public class HelloWorld {
        public static void main(String[] args) {
            System.out.println("Hola, Mundo!");
        }
    }
    ```
    ```

*   **Tablas**: Las tablas no forman parte de la especificación original de Markdown, pero GitHub Flavored Markdown (GFM) y otras variantes las soportan ampliamente. Se construyen usando barras verticales (`|`) para las columnas y guiones (`-`) para el encabezado.
    ```markdown
    | Encabezado 1 | Encabezado 2 | Encabezado 3 |
    |--------------|:------------:|-------------:|
    | Fila 1 Col 1 | Fila 1 Col 2 | Fila 1 Col 3 |
    | Fila 2 Col 1 | Fila 2 Col 2 | Fila 2 Col 3 |
    | Fila 3 Col 1 | Fila 3 Col 2 | Fila 3 Col 3 |
    ```
    *Alineación*: Los dos puntos en la línea de guiones controlan la alineación del texto:
    *   `:---` o `---` = Izquierda
    *   `:---:` = Centro
    *   `---:` = Derecha

#### Ejemplo de Documento Markdown Completo

A continuación, un ejemplo de cómo se vería un documento `README.md` estructurado utilizando Markdown:

```markdown
# Mi Proyecto Fabuloso

¡Bienvenido a Mi Proyecto Fabuloso! Este es un proyecto de ejemplo que demuestra cómo usar Markdown para la documentación.

## 🚀 Inicio Rápido

Sigue estos pasos para poner en marcha el proyecto en tu entorno local.

### Prerequisitos

Asegúrate de tener instalado lo siguiente:

*   Node.js (versión 14 o superior)
*   npm (normalmente viene con Node.js)
*   Git

### Instalación

1.  **Clona el repositorio:**
    ```bash
    git clone https://github.com/tu-usuario/mi-proyecto-fabuloso.git
    cd mi-proyecto-fabuloso
    ```

2.  **Instala las dependencias:**
    ```bash
    npm install
    ```

3.  **Ejecuta el proyecto:**
    ```bash
    npm start
    ```
    El proyecto debería estar ahora ejecutándose en `http://localhost:3000`.

## 📚 Estructura del Proyecto

El proyecto está organizado de la siguiente manera:

*   `src/`: Contiene el código fuente principal.
    *   `components/`: Componentes UI reutilizables.
    *   `pages/`: Vistas de la aplicación.
    *   `App.js`: Componente principal de la aplicación.
    *   `index.js`: Punto de entrada de la aplicación.
*   `public/`: Archivos estáticos como `index.html` y `favicon.ico`.
*   `README.md`: Este mismo archivo de documentación.

## 🛠️ Comandos Útiles

Aquí hay una tabla de comandos que te pueden ser útiles durante el desarrollo:

| Comando           | Descripción                                         |
|-------------------|:----------------------------------------------------|
| `npm start`       | Inicia el servidor de desarrollo local.             |
| `npm test`        | Ejecuta los tests unitarios.                        |
| `npm run build`   | Compila la aplicación para producción.              |
| `npm run deploy`  | Despliega la aplicación a un entorno de staging.    |
| `git status`      | Muestra el estado del repositorio.                  |
| `git commit -m ""`| Guarda los cambios en el historial.                 |

## 🤝 Contribución

¡Las contribuciones son bienvenidas! Si deseas contribuir, sigue estos pasos:

1.  Haz un `fork` de este repositorio.
2.  Crea una nueva rama para tu característica:
    ```bash
    git checkout -b feature/nombre-de-la-caracteristica
    ```
3.  Realiza tus cambios y `commitea` con un mensaje descriptivo.
4.  Sube tu rama:
    ```bash
    git push origin feature/nombre-de-la-caracteristica
    ```
5.  Abre un `Pull Request` explicando tus cambios.

### Pautas para Commits

Por favor, sigue estas pautas para los mensajes de commit:

*   Comienza con un verbo imperativo (ej., "Añadir", "Corregir", "Actualizar").
*   Mantén la primera línea corta (menos de 50 caracteres).
*   Proporciona un cuerpo más detallado si es necesario, explicando el "por qué" y "cómo".

## 📜 Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo `LICENSE` para más detalles.

## 📞 Contacto

Para cualquier pregunta o comentario, puedes contactar a [Tu Nombre](mailto:tu.email@ejemplo.com).
```

## 2.2. JavaDoc (Java)

**Javadoc** es una utilidad desarrollada por Oracle que **genera documentación de APIs en formato HTML a partir del código fuente Java**. Es ampliamente reconocido como el estándar de la industria para documentar clases, interfaces, métodos y miembros en proyectos Java. La documentación generada por Javadoc permite a otros programadores comprender y utilizar una clase o API simplemente revisando su interfaz, sin necesidad de leer o estudiar su implementación interna.

### Comentarios y Etiquetas en Javadoc

Los comentarios Javadoc se escriben utilizando una sintaxis especial que comienza con `/**` y termina con `*/`. Deben colocarse inmediatamente antes de la declaración de una clase, interfaz, método o miembro al que se desea documentar. Dentro de estos comentarios, se utilizan "etiquetas" (tags) especiales, precedidas por el símbolo `@`, para estructurar la información. También se admite la inclusión de etiquetas HTML para un formato más rico.

**Etiquetas Javadoc Comunes:**

*   **`@author`**: Utilizada para documentar la clase o interfaz, indicando el autor o autores.
*   **`@version`**: Utilizada para documentar la versión del método o clase.
*   **`@param <nombre_parametro> <descripción>`**: Describe un parámetro de un método o constructor. `<nombre_parametro>` es el nombre del parámetro, y `<descripción>` explica su propósito.
*   **`@return <descripción>`**: Describe el valor devuelto por un método. Solo se usa en métodos de tipo función (que no son `void`).
*   **`@throws <clase_excepción> <descripción>` / `@exception <clase_excepción> <descripción>`**: Documenta las excepciones que un método puede lanzar.
*   **`@see <referencia>`**: Permite referenciar otra documentación, clases o enlaces web. La referencia puede ser a otro método (`#método()`), una clase (`clase`), un paquete (`paquete.clase`), o una URL (`<a href="URL">texto</a>`).
*   **`@deprecated <descripción>`**: Indica que una parte del código (clase, método, etc.) está obsoleta y no debería usarse. La descripción debería indicar por qué está obsoleta y qué alternativa usar.
*   **`{@code <código>}`**: Muestra un fragmento de código o texto con fuente de tipo código, sin interpretar etiquetas HTML dentro. Similar a la comilla invertida en Markdown.
*   **`{@link <referencia>}`**: Crea un enlace en línea a otra parte de la documentación.

#### Ejemplo de Clase Java Documentada con Javadoc

Consideremos una clase `Producto` con propiedades y métodos para gestionar un inventario básico.

```java
/**
 * La clase `Producto` representa un artículo individual en un inventario.
 * Cada producto tiene un identificador único, un nombre, un precio y una cantidad en stock.
 * Proporciona métodos para acceder y modificar sus atributos, así como para gestionar el stock.
 *
 * @author Tu Nombre
 * @version 1.0.0
 * @see <a href="https://ejemplo.com/docs/productos">Documentación de la API de Productos</a>
 */
public class Producto {

    private String id;
    private String nombre;
    private double precio;
    private int cantidadEnStock;

    /**
     * Constructor para crear un nuevo objeto `Producto`.
     *
     * @param id             El identificador único del producto (no puede ser nulo o vacío).
     * @param nombre         El nombre del producto (no puede ser nulo o vacío).
     * @param precio         El precio unitario del producto (debe ser mayor que cero).
     * @param cantidadEnStock La cantidad inicial de este producto en stock (debe ser no negativa).
     * @throws IllegalArgumentException Si el id, nombre es nulo/vacío, o el precio/cantidad es inválido.
     */
    public Producto(String id, String nombre, double precio, int cantidadEnStock) {
        if (id == null || id.trim().isEmpty()) {
            throw new IllegalArgumentException("El ID del producto no puede ser nulo o vacío.");
        }
        if (nombre == null || nombre.trim().isEmpty()) {
            throw new IllegalArgumentException("El nombre del producto no puede ser nulo o vacío.");
        }
        if (precio <= 0) {
            throw new IllegalArgumentException("El precio del producto debe ser mayor que cero.");
        }
        if (cantidadEnStock < 0) {
            throw new IllegalArgumentException("La cantidad en stock no puede ser negativa.");
        }

        this.id = id;
        this.nombre = nombre;
        this.precio = precio;
        this.cantidadEnStock = cantidadEnStock;
    }

    /**
     * Obtiene el identificador único del producto.
     *
     * @return El {@code String} que representa el ID del producto.
     */
    public String getId() {
        return id;
    }

    /**
     * Obtiene el nombre del producto.
     *
     * @return El {@code String} que representa el nombre del producto.
     */
    public String getNombre() {
        return nombre;
    }

    /**
     * Establece un nuevo nombre para el producto.
     *
     * @param nombre El nuevo nombre del producto (no puede ser nulo o vacío).
     * @throws IllegalArgumentException Si el nombre proporcionado es nulo o vacío.
     */
    public void setNombre(String nombre) {
        if (nombre == null || nombre.trim().isEmpty()) {
            throw new IllegalArgumentException("El nombre del producto no puede ser nulo o vacío.");
        }
        this.nombre = nombre;
    }

    /**
     * Obtiene el precio unitario del producto.
     *
     * @return El {@code double} que representa el precio del producto.
     */
    public double getPrecio() {
        return precio;
    }

    /**
     * Establece un nuevo precio para el producto.
     *
     * @param precio El nuevo precio del producto (debe ser mayor que cero).
     * @throws IllegalArgumentException Si el precio proporcionado es menor o igual a cero.
     */
    public void setPrecio(double precio) {
        if (precio <= 0) {
            throw new IllegalArgumentException("El precio del producto debe ser mayor que cero.");
        }
        this.precio = precio;
    }

    /**
     * Obtiene la cantidad actual de este producto en stock.
     *
     * @return El {@code int} que representa la cantidad en stock.
     */
    public int getCantidadEnStock() {
        return cantidadEnStock;
    }

    /**
     * Añade una cantidad específica al stock del producto.
     *
     * @param cantidad La cantidad a añadir al stock (debe ser positiva).
     * @throws IllegalArgumentException Si la cantidad a añadir es menor o igual a cero.
     */
    public void añadirStock(int cantidad) {
        if (cantidad <= 0) {
            throw new IllegalArgumentException("La cantidad a añadir debe ser positiva.");
        }
        this.cantidadEnStock += cantidad;
    }

    /**
     * Retira una cantidad específica del stock del producto.
     *
     * @param cantidad La cantidad a retirar del stock (debe ser positiva).
     * @throws IllegalArgumentException Si la cantidad a retirar es menor o igual a cero,
     *                                  o si no hay suficiente stock.
     * @throws IllegalStateException    Si la cantidad a retirar excede la cantidad en stock.
     */
    public void retirarStock(int cantidad) {
        if (cantidad <= 0) {
            throw new IllegalArgumentException("La cantidad a retirar debe ser positiva.");
        }
        if (this.cantidadEnStock < cantidad) {
            throw new IllegalStateException("No hay suficiente stock para retirar esta cantidad. Stock actual: " + this.cantidadEnStock);
        }
        this.cantidadEnStock -= cantidad;
    }

    /**
     * Representación en formato String del objeto Producto.
     *
     * @return Un {@code String} que contiene el ID, nombre, precio y cantidad en stock del producto.
     */
    @Override
    public String toString() {
        return "Producto{" +
               "id='" + id + '\'' +
               ", nombre='" + nombre + '\'' +
               ", precio=" + precio +
               ", cantidadEnStock=" + cantidadEnStock +
               '}';
    }
}
```

## 2.3. XMLdoc (C#)

**XMLdoc** es el mecanismo que C# ofrece para **documentar el código utilizando una sintaxis de comentarios que contiene texto en formato XML**. Estos comentarios se procesan mediante una herramienta generadora de documentación (a menudo el propio compilador de C#) para producir un archivo XML de documentación. Este archivo XML es luego utilizado por un visor de documentación para presentar la información de manera tipográfica y legible, facilitando la comprensión de las APIs y los tipos definidos por el usuario.

### Sintaxis y Generación en XMLdoc

Los comentarios de documentación XML en C# deben comenzar con `///` para comentarios de una sola línea o `/** ... */` para comentarios delimitados. Deben colocarse inmediatamente antes de un tipo definido por el usuario (como una clase, delegado o interfaz) o un miembro (como un campo, evento, propiedad o método). Las secciones de atributos se consideran parte de las declaraciones, por lo que los comentarios de documentación deben preceder a los atributos aplicados a un tipo o miembro.

El compilador de C# puede generar automáticamente el archivo XML de documentación durante la compilación si se le indica (generalmente con la opción `/doc` en el compilador o configurando la propiedad correspondiente en el archivo `.csproj`).

### Etiquetas XMLdoc Recomendadas

XMLdoc acepta cualquier etiqueta XML válida, pero sugiere un conjunto de etiquetas estándar para usos comunes:

*   **`<summary>`**: Proporciona una descripción breve y concisa de un tipo o miembro. Es el uso más común y fundamental.
*   **`<remarks>`**: Describe información adicional sobre un tipo o miembro, complementando el `<summary>`. Puede ser más detallado y extenso.
*   **`<param name="nombre_parametro">descripción</param>`**: Describe un parámetro de un método o constructor.
*   **`<returns>descripción</returns>`**: Describe el valor devuelto por un método.
*   **`<exception cref="tipo_excepción">descripción</exception>`**: Identifica las excepciones que un método puede lanzar. El atributo `cref` se usa para referenciar el tipo de excepción, y la herramienta de documentación puede verificar que exista.
*   **`<example>código de ejemplo</example>`**: Indica un ejemplo de cómo usar un método u otro miembro. Por lo general, se usa junto con la etiqueta `<code>`.
*   **`<code>código fuente o salida del programa</code>`**: Presenta una o más líneas de código fuente o salida del programa con una fuente especial. Para fragmentos pequeños de código dentro de un texto narrativo, se usa `<c>texto</c>`.
*   **`<see cref="miembro"/>`**: Especifica un vínculo en línea a otro miembro de código. El atributo `cref` se usa para la referencia.
*   **`<seealso cref="miembro"/>`**: Genera una entrada en una sección de "Consulte también", útil para referencias relacionadas.
*   **`<value>descripción de la propiedad</value>`**: Describe una propiedad.
*   **`<list type="bullet" | "number" | "table">...</list>`**: Crea listas o tablas estructuradas.
*   **`<para>contenido</para>`**: Permite agregar estructura (párrafos) dentro de otras etiquetas.
*   **`<include file="docs.xml" path='extradoc/class[@name="IntList"]/*'/>`**: Permite incluir información desde un archivo XML externo. Útil para separar la documentación extensa del código fuente.
*   **`<typeparam name="nombre_parametro_tipo">descripción</typeparam>`**: Describe un parámetro de tipo para un tipo o método genérico.
*   **`<typeparamref name="nombre_parametro_tipo"/>`**: Identifica una palabra como el nombre de un parámetro de tipo, que puede mostrarse con un formato distintivo.

El atributo `cref` es particularmente importante, ya que se puede asociar a cualquier etiqueta para proporcionar una referencia a un elemento de código. El generador de documentación verifica que el elemento de código exista. Para elementos de código genéricos, se pueden usar llaves (`List{T}`) o la sintaxis de escape XML (`List&lt;T&gt;`) en el `cref`.

#### Ejemplo de Clase C# Documentada con XMLdoc

Utilizaremos la misma clase `Producto` para mostrar la documentación en C#.

```csharp
using System;

/// <summary>
/// La clase <c>Producto</c> representa un artículo individual en un inventario.
/// Cada producto tiene un identificador único, un nombre, un precio y una cantidad en stock.
/// Proporciona métodos para acceder y modificar sus atributos, así como para gestionar el stock.
/// </summary>
/// <remarks>
/// Esta clase es fundamental para la gestión de inventario y asegura la encapsulación
/// de los detalles del producto.
/// </remarks>
/// <seealso cref="System.String"/>
/// <seealso href="https://ejemplo.com/docs/productos">Documentación de la API de Productos</seealso>
public class Producto
{
    /// <summary>
    /// Obtiene el identificador único del producto.
    /// </summary>
    /// <value>Un <see cref="System.String"/> que representa el ID del producto.</value>
    public string Id { get; private set; }

    /// <summary>
    /// Obtiene o establece el nombre del producto.
    /// </summary>
    /// <value>Un <see cref="System.String"/> que representa el nombre del producto.</value>
    /// <exception cref="System.ArgumentException">
    /// Se lanza cuando el nombre proporcionado es nulo o vacío.
    /// </exception>
    public string Nombre
    {
        get { return _nombre; }
        set
        {
            if (string.IsNullOrWhiteSpace(value))
            {
                throw new ArgumentException("El nombre del producto no puede ser nulo o vacío.");
            }
            _nombre = value;
        }
    }
    private string _nombre;

    /// <summary>
    /// Obtiene o establece el precio unitario del producto.
    /// </summary>
    /// <value>Un <see cref="System.Double"/> que representa el precio del producto.</value>
    /// <exception cref="System.ArgumentException">
    /// Se lanza cuando el precio proporcionado es menor o igual a cero.
    /// </exception>
    public double Precio
    {
        get { return _precio; }
        set
        {
            if (value <= 0)
            {
                throw new ArgumentException("El precio del producto debe ser mayor que cero.");
            }
            _precio = value;
        }
    }
    private double _precio;

    /// <summary>
    /// Obtiene la cantidad actual de este producto en stock.
    /// </summary>
    /// <value>Un <see cref="System.Int32"/> que representa la cantidad en stock.</value>
    public int CantidadEnStock { get; private set; }

    /// <summary>
    /// Constructor para crear un nuevo objeto <c>Producto</c>.
    /// </summary>
    /// <param name="id">El identificador único del producto (no puede ser nulo o vacío).</param>
    /// <param name="nombre">El nombre del producto (no puede ser nulo o vacío).</param>
    /// <param name="precio">El precio unitario del producto (debe ser mayor que cero).</param>
    /// <param name="cantidadEnStock">La cantidad inicial de este producto en stock (debe ser no negativa).</param>
    /// <exception cref="System.ArgumentException">
    /// Si el id, nombre es nulo/vacío, o el precio/cantidad es inválido.
    /// </exception>
    /// <example>
    /// Este es un ejemplo de cómo instanciar un producto:
    /// <code>
    /// Producto miProducto = new Producto("P001", "Laptop", 1200.50, 10);
    /// Console.WriteLine(miProducto.Nombre); // Salida: Laptop
    /// </code>
    /// </example>
    public Producto(string id, string nombre, double precio, int cantidadEnStock)
    {
        if (string.IsNullOrWhiteSpace(id))
        {
            throw new ArgumentException("El ID del producto no puede ser nulo o vacío.");
        }
        if (string.IsNullOrWhiteSpace(nombre))
        {
            throw new ArgumentException("El nombre del producto no puede ser nulo o vacío.");
        }
        if (precio <= 0)
        {
            throw new ArgumentException("El precio del producto debe ser mayor que cero.");
        }
        if (cantidadEnStock < 0)
        {
            throw new ArgumentException("La cantidad en stock no puede ser negativa.");
        }

        Id = id;
        _nombre = nombre; // Asignación directa para evitar llamada a set que validaría de nuevo
        _precio = precio; // Asignación directa
        CantidadEnStock = cantidadEnStock;
    }

    /// <summary>
    /// Añade una cantidad específica al stock del producto.
    /// </summary>
    /// <param name="cantidad">La cantidad a añadir al stock (debe ser positiva).</param>
    /// <exception cref="System.ArgumentException">
    /// Se lanza si la cantidad a añadir es menor o igual a cero.
    /// </exception>
    public void AnadirStock(int cantidad)
    {
        if (cantidad <= 0)
        {
            throw new ArgumentException("La cantidad a añadir debe ser positiva.");
        }
        CantidadEnStock += cantidad;
    }

    /// <summary>
    /// Retira una cantidad específica del stock del producto.
    /// </summary>
    /// <param name="cantidad">La cantidad a retirar del stock (debe ser positiva).</param>
    /// <exception cref="System.ArgumentException">
    /// Se lanza si la cantidad a retirar es menor o igual a cero.
    /// </exception>
    /// <exception cref="System.InvalidOperationException">
    /// Se lanza si la cantidad a retirar excede la cantidad en stock.
    /// </exception>
    public void RetirarStock(int cantidad)
    {
        if (cantidad <= 0)
        {
            throw new ArgumentException("La cantidad a retirar debe ser positiva.");
        }
        if (CantidadEnStock < cantidad)
        {
            throw new InvalidOperationException($"No hay suficiente stock para retirar esta cantidad. Stock actual: {CantidadEnStock}");
        }
        CantidadEnStock -= cantidad;
    }

    /// <summary>
    /// Representación en formato String del objeto Producto.
    /// </summary>
    /// <returns>Un <see cref="System.String"/> que contiene el ID, nombre, precio y cantidad en stock del producto.</returns>
    public override string ToString()
    {
        return $"Producto{{Id='{Id}', Nombre='{Nombre}', Precio={Precio}, CantidadEnStock={CantidadEnStock}}}";
    }
}
```

## Autor

Codificado con :sparkling_heart: por [José Luis González Sánchez](https://twitter.com/JoseLuisGS_)

[![Twitter](https://img.shields.io/twitter/follow/JoseLuisGS_?style=social)](https://twitter.com/JoseLuisGS_)
[![GitHub](https://img.shields.io/github/followers/joseluisgs?style=social)](https://github.com/joseluisgs)
[![GitHub](https://img.shields.io/github/stars/joseluisgs?style=social)](https://github.com/joseluisgs)


### Contacto

<p>
  Cualquier cosa que necesites házmelo saber por si puedo ayudarte 💬.
</p>
<p>
 <a href="https://joseluisgs.dev" target="_blank">
        <img src="https://joseluisgs.github.io/img/favicon.png" 
    height="30">
    </a>  &nbsp;&nbsp;
    <a href="https://github.com/joseluisgs" target="_blank">
        <img src="https://distreau.com/github.svg" 
    height="30">
    </a> &nbsp;&nbsp;
        <a href="https://twitter.com/JoseLuisGS_" target="_blank">
        <img src="https://i.imgur.com/U4Uiaef.png" 
    height="30">
    </a> &nbsp;&nbsp;
    <a href="https://www.linkedin.com/in/joseluisgonsan" target="_blank">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/ca/LinkedIn_logo_initials.png/768px-LinkedIn_logo_initials.png" 
    height="30">
    </a>  &nbsp;&nbsp;
    <a href="https://g.dev/joseluisgs" target="_blank">
        <img loading="lazy" src="https://googlediscovery.com/wp-content/uploads/google-developers.png" 
    height="30">
    </a>  &nbsp;&nbsp;
<a href="https://www.youtube.com/@joseluisgs" target="_blank">
        <img loading="lazy" src="https://upload.wikimedia.org/wikipedia/commons/e/ef/Youtube_logo.png" 
    height="30">
    </a>  
</p>

## Licencia de uso

Este repositorio y todo su contenido está licenciado bajo licencia **Creative Commons**, si desea saber más, vea
la [LICENSE](https://joseluisgs.dev/docs/license/). Por favor si compartes, usas o modificas este proyecto cita a su
autor, y usa las mismas condiciones para su uso docente, formativo o educativo y no comercial.

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Licencia de Creative Commons" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" property="dct:title">
JoseLuisGS</span>
by <a xmlns:cc="http://creativecommons.org/ns#" href="https://joseluisgs.dev/" property="cc:attributionName" rel="cc:attributionURL">
José Luis González Sánchez</a> is licensed under
a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons
Reconocimiento-NoComercial-CompartirIgual 4.0 Internacional License</a>.<br />Creado a partir de la obra
en <a xmlns:dct="http://purl.org/dc/terms/" href="https://github.com/joseluisgs" rel="dct:source">https://github.com/joseluisgs</a>.
