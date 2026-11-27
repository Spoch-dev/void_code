# Seguridad

## Cómo avisar de un fallo

Si encuentras un fallo de seguridad en Void Code, **no abras un issue público**. Avísame en
privado desde GitHub:

1. Ve a la pestaña **Security** del repositorio.
2. Pulsa **Report a vulnerability**
   ([enlace directo](https://github.com/Spoch-dev/void_code/security/advisories/new)).
3. Cuenta qué pasa, cómo reproducirlo y qué versión usas.

Intentaré responder en unos días. Cuando esté corregido, publicaré un aviso explicando el
fallo, y te mencionaré si quieres.

## Versiones con soporte

Solo se corrigen fallos en la última versión publicada.

## Qué cuenta como fallo de seguridad

Por ejemplo:

- Que la app filtre el token de GitHub (en registros, en la línea de órdenes de un proceso, en
  archivos o en la red fuera de github.com).
- Que abrir un archivo o una carpeta haga que se ejecute código sin que lo pidas.
- Que la sesión de GitHub de Void Code se use para algo más de lo que pide el usuario.

## Sesión de GitHub

Void Code guarda su token de GitHub en el llavero del sistema (Administrador de credenciales en
Windows, Secret Service en Linux), nunca en archivos de configuración. Al hablar con la API se lo
pasa a `curl` por la entrada estándar, y a `git` por variables de entorno, de modo que no aparece
en la lista de procesos. El identificador de la OAuth App no es un secreto (OAuth lo considera
público).
