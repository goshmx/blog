---
layout: post
title: Instalar Ruby 3 en macOS
---

### Instalar Ruby 3 en macOS

Llevó un tiempo en un proyecto que utiliza la version 3 de ruby, y no había tenido mayor dificultad, hasta que me toco instalarlo en mi Macbook Pro con M2.
Estuve intentando con homebrew, utilizando RVM, pero generaba un error de OPENSSL, así que me decanté por utilizar rbenv.

Para instalar rbenv, se debe ejecutar el siguiente comando:

```bash
brew install rbenv ruby-build
```

Luego de instalar rbenv, se debe agregar la siguiente linea al archivo `~/.zshrc`:

```bash
export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init -)"
```

Luego de agregar la linea al archivo `~/.zshrc`, se debe ejecutar el siguiente comando:

```bash
source ~/.zshrc
```

Luego de ejecutar el comando, se debe instalar la version de ruby que se desea, en este caso la version 3.0.6:

```bash
rbenv install 3.0.6
```

Luego de instalar la version de ruby, se debe establecer la version de ruby como la version global:

```bash
rbenv global 3.0.6
```

Luego de establecer la version de ruby como la version global, se debe verificar la version de ruby:

```bash
ruby -v
```

Y listo! Ya se tiene instalado ruby 3 en macOS.
