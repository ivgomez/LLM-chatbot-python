# Useful Python Commands

## Create and activate a virtual environment in one line

```bash
python3 -m venv .venv ; source .venv/bin/activate
```

## Deactivate the virtual environment

```bash
deactivate
```

## Verify the virtual environment is active

```bash
echo $VIRTUAL_ENV
which python
```

## Install dependencies

```bash
pip3 install -r requirements.txt
python3 -m pip install <package>
```

**Note:** the `-m` flag runs a Python module as a script (for example, `python3 -m pip` uses the `pip` tied to the active interpreter).

### Parameters explained

- `python3`: the Python 3 interpreter you are invoking.
- `-m`: runs a module as a script using the active interpreter.
- `pip`: the package installer module.
- `install`: installs packages.
- `-r requirements.txt`: reads a list of packages from a file.
- `<package>`: placeholder for a package name (for example, `requests`).

## Run Python scripts

```bash
python3 app.py
python3 -m module_name
```

### Parameters explained

- `python3`: the Python 3 interpreter.
- `app.py`: the script file you want to run.
- `-m`: run a module as a script.
- `module_name`: the importable module/package to execute (for example, `http.server`).

---

# More useful commands (with parameter explanations)

## Upgrade pip

```bash
python3 -m pip install --upgrade pip
```

### Parameters explained

- `python3`: the Python 3 interpreter.
- `-m`: run a module as a script.
- `pip`: the package installer module.
- `install`: installs packages.
- `--upgrade`: updates an installed package to the latest version.
- `pip`: the package name to upgrade.

## Create requirements.txt from the current environment

```bash
python3 -m pip freeze > requirements.txt
```

### Parameters explained

- `python3`: the Python 3 interpreter.
- `-m`: run a module as a script.
- `pip`: the package installer module.
- `freeze`: outputs installed packages and versions.
- `>`: redirects output into a file.
- `requirements.txt`: the file to write.

## List installed packages

```bash
python3 -m pip list
```

### Parameters explained

- `python3`: the Python 3 interpreter.
- `-m`: run a module as a script.
- `pip`: the package installer module.
- `list`: shows installed packages.

## Show details of a package

```bash
python3 -m pip show <package>
```

### Parameters explained

- `python3`: the Python 3 interpreter.
- `-m`: run a module as a script.
- `pip`: the package installer module.
- `show`: displays package metadata.
- `<package>`: placeholder for a package name.

## Uninstall a package

```bash
python3 -m pip uninstall <package>
```

### Parameters explained

- `python3`: the Python 3 interpreter.
- `-m`: run a module as a script.
- `pip`: the package installer module.
- `uninstall`: removes a package.
- `<package>`: placeholder for a package name.

## Run a module from the standard library (quick local server)

```bash
python3 -m http.server 8000
```

### Parameters explained

- `python3`: the Python 3 interpreter.
- `-m`: run a module as a script.
- `http.server`: standard library module for a simple HTTP server.
- `8000`: the port number to serve on.

## Print the active Python executable

```bash
python3 -c "import sys; print(sys.executable)"
```

### Parameters explained

- `python3`: the Python 3 interpreter.
- `-c`: run the following string as Python code.
- `"import sys; print(sys.executable)"`: the Python code to execute.

## Run a script with arguments

```bash
python3 script.py --input file.txt --verbose
```

### Parameters explained

- `python3`: the Python 3 interpreter.
- `script.py`: the script file to run.
- `--input`: example named argument (your script must parse it).
- `file.txt`: the value passed to `--input`.
- `--verbose`: example flag argument (on/off).

## Run tests with pytest

```bash
python3 -m pytest -q
```

### Parameters explained

- `python3`: the Python 3 interpreter.
- `-m`: run a module as a script.
- `pytest`: the test runner module.
- `-q`: quiet output (less verbose).

## Format code with black

```bash
python3 -m black .
```

### Parameters explained

- `python3`: the Python 3 interpreter.
- `-m`: run a module as a script.
- `black`: the formatter module.
- `.`: current directory (format all files under it).

## Sort imports with isort

```bash
python3 -m isort .
```

### Parameters explained

- `python3`: the Python 3 interpreter.
- `-m`: run a module as a script.
- `isort`: the import sorter module.
- `.`: current directory.

---

# Rename the path in the prompt (Zsh)

## Fixed (persistent) in Zsh

If you want it to show your username + current folder:

```bash
export PS1="%F{green}[%n%f: %F{blue}i.gomez → %1~%f]%# "
```

If you want an emoji + folder:

```bash
export PS1="%F{green}[%n%f: %F{blue}📁 %1~%f]%# "
```

If you want only fixed text (no changes while navigating):

```bash
export PS1="%F{green}[%n%f: %F{blue}My Project%f]%# "
```

**Important:** Everything between `%F{blue}` and `%f` (the blue color) is what shows as the "path". Replace that content with whatever you want.

Reload the configuration:

```bash
source ~/.zshrc
```

## Temporary (session-only) in Zsh

Option 1: With your username and current folder:

```bash
export PS1="%F{green}[%n%f: %F{blue}i.gomez → %1~%f]%# "
```

Option 2: With emoji and current folder:

```bash
export PS1="%F{green}[%n%f: %F{blue}📁 %1~%f]%# "
```

Option 3: Fixed text only (no changes while navigating):

```bash
export PS1="%F{green}[%n%f: %F{blue}My Project%f]%# "
```

Option 4: With time included:

```bash
export PS1="%F{green}[%n%f: %F{blue}%1~%f %F{yellow}(%D{%H:%M})%f]%# "
```

---

# Rename the path in the prompt (Bash)

## Fixed (persistent) in Bash

If you want it to show your username + current folder:

```bash
export PS1="[\u: \w]$ "
```

If you want an emoji + folder:

```bash
export PS1="[\u: 📁 \w]$ "
```

If you want only fixed text (no changes while navigating):

```bash
export PS1="[My Project]$ "
```

Reload the configuration:

```bash
source ~/.bashrc
```

> On macOS you might also use `~/.bash_profile` depending on your setup.

## Temporary (session-only) in Bash

Option 1: With your username and current folder:

```bash
export PS1="[\u: \w]$ "
```

Option 2: With emoji and current folder:

```bash
export PS1="[\u: 📁 \w]$ "
```

Option 3: Fixed text only (no changes while navigating):

```bash
export PS1="[My Project]$ "
```

Option 4: With time included:

```bash
export PS1="[\u: \w] (\t)$ "
```

**Tip:** In Bash, `\u` = username, `\w` = full path, `\W` = current folder, `\t` = time (HH:MM:SS).
