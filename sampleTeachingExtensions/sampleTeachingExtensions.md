---
header-includes:
      - \usepackage{color}
      - \definecolor{gray}{rgb}{0.1,0.5,0.2}
---

# Extensiones para enseñanza ||| Teaching extensions

## Tamaños de fuente personalizados ||| Custom fontsizes

BEGIN-SP

Este es el modo en el que podemos conseguir fuentes [más grandes]{fontsize=huge}, o [más pequeñas]{fontsize=tiny}.

END-SP

BEGIN-EN

This is the way to get [bigger]{fontsize} fonts or [smaller]{fontsize=tiny}.

END-EN

# Alineamiento ||| Alignment

BEGIN-SP

<div align="left">
A la izquierda.
</div>

<div align="center">
centrado
</div>

<div align="right">
A la derecha.
</div>

END-SP

BEGIN-EN

<div align="left">
On the left...
</div>

<div align="center">
centered
</div>

<div align="right">
on the right.
</div>

END-EN

# Formatos adicionales ||| Additional formats

BEGIN-SP

Podemos crear [texto subrayado]{.underline}.

[¡O resaltado!]{.alert}

[O incluso en color]{color=gray}

END-SP

BEGIN-EN

We can write [underlined text]{.underline}.

[Or highlighted!]{.alert}

[Or even colored]{color=gray}

END-EN


# Salto de página ||| Inserting a pagebreak

### {.pagebreak}


# Soporte para múltiples columnas ||| Multiple columns support

BEGIN-SP

<div class="columns" colsep="0.3cm">

**Esta es una sección con múltiples columnas:**

<div class="column" width="25%">
Esta sería la primera columna.
</div>

<div class="column" width="30%">
Una segunda, un poco más ancha.
</div>

<div class="column" width="25%">
Y una tercera.
</div>

</div>

END-SP

BEGIN-EN

<div class="columns" colsep="0.3cm">

**This is a multi-column section:**

<div class="column" width="25%">
Here, we have the first column.
</div>

<div class="column" width="30%">
Now the second, a bit wider.
</div>

<div class="column" width="25%">
And a third one.
</div>

</div>

END-EN


# Bloques sombreados ||| Shaded blocks

BEGIN-SP

<div class="shaded">

Selecciona la respuesta correcta:

a. Uno
b. Dos
c. Tres
d. Cuatro

</div>

END-SP

BEGIN-EN

<div class="shaded">

Select the correct option:

a. Option 1
b. Option 1
c. Option 3 
d. Option 4

</div>

END-EN
