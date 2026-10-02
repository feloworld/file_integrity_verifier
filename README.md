# Verificador de Integridad de Archivos

Este programa permite calcular y verificar el hash SHA-256 de un archivo para comprobar si su contenido ha cambiado o se ha corrompido.

## ¿Qué hace?

La herramienta ofrece un menú interactivo con estas opciones:

1. Calcular y mostrar el hash SHA-256 de un archivo.
2. Comparar el hash actual con un hash esperado para verificar la integridad del archivo.
3. Salir del programa.

Se usa principalmente para validar si un archivo original y una copia o versión posterior siguen siendo idénticas, sin necesidad de comparar el contenido completo byte a byte.

## ¿Cómo funciona?

El programa:

- recibe la ruta de un archivo;
- lee el contenido en bloques de 64 KB;
- calcula el hash SHA-256 usando la librería `hashlib` de Python;
- devuelve una cadena hexadecimal que representa el contenido del archivo;
- opcionalmente compara ese valor con un hash previamente conocido.

Si el hash calculado coincide con el hash esperado, el archivo se considera intacto. Si no coincide, se indica que el archivo ha cambiado.

## Características principales

- Cálculo eficiente de hash para archivos grandes.
- Lectura en bloques para optimizar memoria y rendimiento.
- Validación de integridad con un hash de referencia.
- Mensajes claros por consola en español.
- Soporta rutas introducidas manualmente o con comillas eliminadas para facilitar arrastrar/soltar archivos.

## Uso

Ejecuta el script:

```bash
python file_integrity_verifier.py
```

A continuación, selecciona una opción del menú:

- Opción 1: calcula el hash SHA-256 del archivo indicado.
- Opción 2: pide la ruta del archivo y el hash esperado; luego compara ambos.

## Ejemplo

Supongamos que tienes un archivo `documento.pdf` y quieres comprobar si ha sido alterado. 

1. Ejecuta el programa.
2. Elige la opción 2.
3. Introduce la ruta del archivo.
4. Introduce el hash SHA-256 original.
5. El programa muestra si la verificación fue exitosa o si el archivo ha cambiado.

## Requisitos

- Python 3
- Sistema operativo con acceso a archivos locales

## Ejemplo de salida

```text
     VERIFICADOR DE INTEGRIDAD (HASH)
1. Calcular y mostrar el Hash SHA-256 de un archivo
2. Comparar con Hash proporcionado (Verificar Integridad)
3. Salir
```

## Importancia

Este tipo de verificación es útil en:

- validación de archivos descargados;
- comprobación de integridad de backups;
- seguridad de distribución de archivos;
- detección de modificaciones no autorizadas.

El SHA-256 es una función criptográfica ampliamente utilizada para asegurar que el contenido de un archivo no haya sido alterado.
