## Git: Sistema de Control de Versiones Distribuido

Git es un sistema de control de versiones distribuido que permite llevar un historial detallado de los cambios en un proyecto. Su código fuente está disponible en [GitHub](http://git-scm.com).  
Fue creado por Linus Torvalds, con su primera versión lanzada el 7 de abril de 2005. Git viene instalado por defecto en sistemas operativos basados en Unix.  
Puedes verificar si tienes Git instalado escribiendo en la terminal:

```git
git --version
```

---

### Configuración de Git

Antes de comenzar, es importante configurar Git con tu información de usuario. Esto se realiza con los siguientes comandos:

```git
git config --global user.name "TuNombre"
git config --global user.email "TuCorreo@correo.com"
```

Estos datos se almacenan en el archivo `.gitconfig` en el directorio personal del usuario.

Para inicializar un repositorio de Git en un proyecto:

```git
git init
```

Esto creará una carpeta oculta `.git` que contiene archivos de configuración de Git.

---

### Ramas en Git

Las ramas permiten trabajar en diferentes versiones del proyecto simultáneamente. Para configurar el nombre de la rama principal:

```git
git config --global init.defaultBranch main
git branch -m main
```

**Comandos básicos relacionados con ramas:**

```git
git branch <nombre-rama>       # Crear una nueva rama
git switch <nombre-rama>       # Cambiar a una rama existente
git merge <nombre-rama>        # Combinar cambios de una rama
```

---

### Seguimiento y Commits

Git utiliza un flujo sencillo para guardar cambios:

1. Agrega archivos al área de preparación (staging area):
    
    ```git
    git add <nombre-archivo>
    ```
    
2. Realiza un commit con un mensaje descriptivo:
    
    ```git
    git commit -m "Mensaje del commit"
    ```
    
3. Visualiza los cambios registrados:
    
    ```git
    git log
    ```
    

Cada commit genera un identificador único (hash) que permite rastrear el historial de cambios.

---

### Visualización de Cambios

- **Para ver los cambios realizados en archivos:**
    
    ```git
    git diff
    ```
    
- **Para cambiar a una versión anterior del proyecto:**
    
    ```git
    git checkout <hash>
    git reset --hard <hash>
    ```
    

> **Nota:** Con `git reflog` puedes ver el historial completo de interacciones, incluso si has revertido cambios.

---

### Alias en Git

Puedes crear alias para simplificar comandos comunes. Por ejemplo:

```git
git config --global alias.tree 'log --graph --decorate --all --oneline'
git tree
```

Esto crea un alias llamado `tree` para visualizar un resumen gráfico del historial de cambios.

---

### Git Ignore

Si no deseas que ciertos archivos sean rastreados por Git, crea un archivo `.gitignore` y añade las rutas o nombres de los archivos:

```gitignore
**/ejemplo.py
```

Luego, realiza un commit para guardar esta configuración:

```git
git add .gitignore
git commit -m "Añadido archivo .gitignore"
```

---

### Resolución de Conflictos

Cuando dos ramas modifican las mismas líneas de un archivo, Git marca un conflicto al intentar hacer un merge. Debes:

1. Resolver manualmente las diferencias en un editor de texto.
2. Agregar los cambios resueltos con `git add`.
3. Realizar un commit para confirmar la resolución.

---

### Git Stash

Guarda cambios temporalmente sin hacer un commit:

```git
git stash             # Guarda los cambios
git stash list        # Lista los cambios guardados
git stash pop         # Recupera el último stash
git stash drop        # Elimina un stash
```

---

### Git Tags

Para etiquetar una versión específica del proyecto:

```git
git tag <etiqueta>
git checkout tags/<etiqueta>
```

---

### Eliminar Ramas

Una vez que termines con una rama, puedes eliminarla:

```git
git branch -d <nombre-rama>
```
