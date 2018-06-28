---
title: "Creación de transparencias Beamer ||| Creating beamer slides"
section-titles: false
toc-per-section: true
fontsize: 11pt
classoption:
- xcolor=table
- c
- slidestop
author:
- ArTeCS group
---

## Aviso ||| Disclaimer

BEGIN-SP

* El presente documento es simplemente un ejemplo

* Puede servir como plantilla para generar una presentación dual

* El contenido mostrado no refleja en detalle los pasos a seguir para generar un documento dual

END-SP

BEGIN-EN

* This document is just an example

* It can be leveraged to generate a simple dual presentation

* The contents are not a guide to generate a dual document

END-EN

## Contenido ||| Contents

\tableofcontents

# Pasos básicos ||| Basic steps

## ¿Cómo crear una presentación dual? ||| How to create a dual presentation?

### Ideas básicas ||| Basic ideas 

BEGIN-SP

* Crear una presentación dual es muy sencillo
* Simplemente necesitamos crear correctamente un fichero `build.yaml` con el siguiente contenido:
    - Especificación de los idiomas deseados
	- Selección de ficheros de entrada Markdown que formarán la presentación
	- Nombre de los ficheros de salida que deseamos generar, en cada uno de los idiomas deseados
	- Parámetros adicionales que den soporte a la generación de los documentos

END-SP

BEGIN-EN

* Creating a dual presentation is straightforward
* We just need to create a `build.yaml` file with the following contents:
	- Specification of target languages
	- Selection of input Markdown files that will conform the presentation
	- Output filenames to generate for every target language
	- Additional parameters to support the document generation process

END-EN
