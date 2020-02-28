Instalación de Python
=====================

En esta guía vamos a ver disintas formas de realizar la instalación de la
la versión específica de Python que se utilizará en la cátedra en los distintos
sistemas operativos.

## Linux y MacOS

Con el objetivo de poder instalar una versión específica de Python que puede
no encontrarse en los gestores de paquetes de Linux o MacOS vamos a utilizar
una herramienta externa llamada `pyenv`

Con `pyenv` no sólo vas a poder instalar una versión de Python en particular
sino que se pueden tener varias versiones de Python en el mismo sistema
operativo. Incluso es posible configurar una versión distinta de Python por
proyecto.

### Instalación con brew (MacOS)

Se puede instalar `pyenv` usando el manejador de paquetes
[Homebrew](https://brew.sh/) para MacOS.

```bash
$ brew update
$ brew install pyenv
```

### Instalación con Git (Linux y MacOS)

Hacer el checkout de `pyenv` en el directorio donde quieras que se instale.
Un buen lugar puede ser `$HOME/.pyenv`.

```bash
$ git clone https://github.com/pyenv/pyenv.git ~/.pyenv
```

Define la variable de entorno `PYENV_ROOT` para tener disponible el path donde
fue clonado el repositorio y agrega `$PYENV_ROOT/bin` a la variable `$PATH` para
tener acceso al comando `pyenv` en la terminal.

```bash
$ echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bash_profile
$ echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bash_profile
```

- Si usas **ZSH** modifica el comando con `~/.zshrc` en lugar de
`~/.bash_profile`.
- Para **Ubuntu** y **Fedora** usa `~/.bashrc` en en lugar de `~/.bash_profile`.

Finalmente para terminar de configurarlo y tener el autocompletado en la consola
ejecuta el siguiente comando:

```bash
$ echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.bash_profile
```

Al igual que en el paso anterior reemplaza con `~/.zshrc` o `~/.bashrc` en el
comando según corresponda.

Luego restartea la terminal para que tome los cambios.

Ahora ya se puede instalar la versión de Python que necesites:

```bash
$ pyenv install 3.6.8
```

Guía completa en el readme del
[repositorio de pyenv](https://github.com/pyenv/pyenv).

### Instalación en Windows

Descarga el instalador [aquí](https://www.python.org/ftp/python/3.6.8/python-3.6.8-amd64-webinstall.exe)

Otros instaladores: https://www.python.org/downloads/release/python-368/
