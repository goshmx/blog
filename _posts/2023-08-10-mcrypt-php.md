---
layout: post
title: Configurar php-mcrypt on macOS usando MAMP
---



### Configurar php-mcrypt on macOS, usando MAMP.

Mcrypt es una biblioteca de cifrado que se usa en PHP. Que si bien su uso ya está obsoleto, aún hay aplicaciones que lo requieren. Es por eso si lo necesitas, aquí te dejo los pasos para instalarlo en macOS.

Para configurar php-mcrypt en macOS, se debe seguir los siguientes pasos:

Instalación usando Homebrew y PECL.

```bash
# Instalación con PHP nativo de macOS
brew install mcrypt
pecl install mcrypt-1.0.3
```

Para usar PECL en una version especifica de PHP de MAMP, se debe usar el siguiente comando:

```bash
# Instalación con version especifica de PHP de MAMP, en este caso la version 7.4.33
/Applications/MAMP/bin/php/php7.4.33/bin/pecl install mcrypt-1.0.3
```

Luego de instalar mcrypt, se debe agregar la extension en el archivo `php.ini` de la version de PHP que se esta usando.

```bash
# Abrir el archivo php.ini
/Applications/MAMP/bin/php/php7.4.33/conf/php.ini
```

```bash
# Agregar la siguiente linea al final del archivo
extension=mcrypt.so
```

Luego de agregar la extension, se debe reiniciar el servidor de MAMP.

```bash
# Reiniciar el servidor de MAMP
/Applications/MAMP/bin/start.sh
```



