# Comandos útiles de Python

## Crear y activar un entorno virtual en una sola línea

```bash
python3 -m venv .venv ; source .venv/bin/activate
```

## Desactivar el entorno virtual

```bash
deactivate
```

## Verificar que el entorno virtual está activo

```bash
echo $VIRTUAL_ENV
which python
```

## Instalar dependencias

```bash
pip3 install -r requirements.txt
python3 -m pip install <paquete>
```

**Nota:** el flag `-m` ejecuta un módulo de Python como script (por ejemplo, `python3 -m pip` usa el `pip` ligado al intérprete activo).

### Parámetros explicados

- `python3`: el intérprete de Python 3 que estás invocando.
- `-m`: ejecuta un módulo como script usando el intérprete activo.
- `pip`: el módulo instalador de paquetes.
- `install`: instala paquetes.
- `-r requirements.txt`: lee una lista de paquetes desde un archivo.
- `<paquete>`: marcador de posición para un paquete (por ejemplo, `requests`).

## Ejecutar scripts de Python

```bash
python3 app.py
python3 -m nombre_del_modulo
```

### Parámetros explicados

- `python3`: el intérprete de Python 3.
- `app.py`: el archivo de script que quieres ejecutar.
- `-m`: ejecuta un módulo como script.
- `nombre_del_modulo`: el módulo/paquete importable a ejecutar (por ejemplo, `http.server`).

---

# Más comandos útiles (con explicación de parámetros)

## Actualizar pip

```bash
python3 -m pip install --upgrade pip
```

### Parámetros explicados

- `python3`: el intérprete de Python 3.
- `-m`: ejecuta un módulo como script.
- `pip`: el módulo instalador de paquetes.
- `install`: instala paquetes.
- `--upgrade`: actualiza un paquete instalado a la última versión.
- `pip`: el nombre del paquete a actualizar.

## Crear requirements.txt desde el entorno actual

```bash
python3 -m pip freeze > requirements.txt
```

### Parámetros explicados

- `python3`: el intérprete de Python 3.
- `-m`: ejecuta un módulo como script.
- `pip`: el módulo instalador de paquetes.
- `freeze`: muestra paquetes instalados y versiones.
- `>`: redirige la salida a un archivo.
- `requirements.txt`: el archivo donde se escribe la salida.

## Listar paquetes instalados

```bash
python3 -m pip list
```

### Parámetros explicados

- `python3`: el intérprete de Python 3.
- `-m`: ejecuta un módulo como script.
- `pip`: el módulo instalador de paquetes.
- `list`: muestra los paquetes instalados.

## Ver detalles de un paquete

```bash
python3 -m pip show <paquete>
```

### Parámetros explicados

- `python3`: el intérprete de Python 3.
- `-m`: ejecuta un módulo como script.
- `pip`: el módulo instalador de paquetes.
- `show`: muestra metadatos del paquete.
- `<paquete>`: marcador de posición para un paquete.

## Desinstalar un paquete

```bash
python3 -m pip uninstall <paquete>
```

### Parámetros explicados

- `python3`: el intérprete de Python 3.
- `-m`: ejecuta un módulo como script.
- `pip`: el módulo instalador de paquetes.
- `uninstall`: elimina un paquete.
- `<paquete>`: marcador de posición para un paquete.

## Ejecutar un módulo de la librería estándar (servidor local rápido)

```bash
python3 -m http.server 8000
```

### Parámetros explicados

- `python3`: el intérprete de Python 3.
- `-m`: ejecuta un módulo como script.
- `http.server`: módulo estándar para un servidor HTTP simple.
- `8000`: el puerto donde servirá.

## Imprimir el ejecutable de Python activo

```bash
python3 -c "import sys; print(sys.executable)"
```

### Parámetros explicados

- `python3`: el intérprete de Python 3.
- `-c`: ejecuta el siguiente string como código Python.
- `"import sys; print(sys.executable)"`: el código Python a ejecutar.

## Ejecutar un script con argumentos

```bash
python3 script.py --input file.txt --verbose
```

### Parámetros explicados

- `python3`: el intérprete de Python 3.
- `script.py`: el archivo de script a ejecutar.
- `--input`: ejemplo de argumento con nombre (tu script debe procesarlo).
- `file.txt`: valor pasado a `--input`.
- `--verbose`: ejemplo de flag (encendido/apagado).

## Ejecutar tests con pytest

```bash
python3 -m pytest -q
```

### Parámetros explicados

- `python3`: el intérprete de Python 3.
- `-m`: ejecuta un módulo como script.
- `pytest`: el módulo del runner de tests.
- `-q`: salida silenciosa (menos verbosa).

## Formatear código con black

```bash
python3 -m black .
```

### Parámetros explicados

- `python3`: el intérprete de Python 3.
- `-m`: ejecuta un módulo como script.
- `black`: el módulo formateador.
- `.`: directorio actual (formatea todo lo que cuelga de él).

## Ordenar imports con isort

```bash
python3 -m isort .
```

### Parámetros explicados

- `python3`: el intérprete de Python 3.
- `-m`: ejecuta un módulo como script.
- `isort`: el módulo para ordenar imports.
- `.`: directorio actual.

---

# Renombrar el path en el prompt (Zsh)

## Fijo (persistente) en Zsh

Si quieres que muestre tu usuario + carpeta actual:

```bash
export PS1="%F{green}[%n%f: %F{blue}i.gomez → %1~%f]%# "
```

Si quieres un emoji + carpeta:

```bash
export PS1="%F{green}[%n%f: %F{blue}📁 %1~%f]%# "
```

Si quieres solo texto fijo (sin cambios al navegar):

```bash
export PS1="%F{green}[%n%f: %F{blue}Mi Proyecto%f]%# "
```

**Importante:** Todo lo que esté entre `%F{blue}` y `%f` (el color azul) es lo que se muestra como "path". Reemplaza ese contenido con lo que quieras.

Recarga la configuración:

```bash
source ~/.zshrc
```

## Temporal (solo para la sesión) en Zsh

Opción 1: Con tu usuario y carpeta actual:

```bash
export PS1="%F{green}[%n%f: %F{blue}i.gomez → %1~%f]%# "
```

Opción 2: Con emoji y carpeta actual:

```bash
export PS1="%F{green}[%n%f: %F{blue}📁 %1~%f]%# "
```

Opción 3: Solo texto fijo (sin cambios al navegar):

```bash
export PS1="%F{green}[%n%f: %F{blue}Mi Proyecto%f]%# "
```

Opción 4: Con hora incluida:

```bash
export PS1="%F{green}[%n%f: %F{blue}%1~%f %F{yellow}(%D{%H:%M})%f]%# "
```

---

# Renombrar el path en el prompt (Bash)

## Fijo (persistente) en Bash

Si quieres que muestre tu usuario + carpeta actual:

```bash
export PS1="[\u: \w]$ "
```

Si quieres un emoji + carpeta:

```bash
export PS1="[\u: 📁 \w]$ "
```

Si quieres solo texto fijo (sin cambios al navegar):

```bash
export PS1="[Mi Proyecto]$ "
```

Recarga la configuración:

```bash
source ~/.bashrc
```

> En macOS también puedes usar `~/.bash_profile` según tu configuración.

## Temporal (solo para la sesión) en Bash

Opción 1: Con tu usuario y carpeta actual:

```bash
export PS1="[\u: \w]$ "
```

Opción 2: Con emoji y carpeta actual:

```bash
export PS1="[\u: 📁 \w]$ "
```

Opción 3: Solo texto fijo (sin cambios al navegar):

```bash
export PS1="[Mi Proyecto]$ "
```

Opción 4: Con hora incluida:

```bash
export PS1="[\u: \w] (\t)$ "
```

**Tip:** En Bash, `\u` = usuario, `\w` = ruta completa, `\W` = carpeta actual, `\t` = hora (HH:MM:SS).
