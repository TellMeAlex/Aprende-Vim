# ¿Nuevo o nueva usando Vim? Lee esto primero

## Por qué se ha escrito este guía

Hay muchos lugares donde aprender a usar Vim: el `vimtutor` es un buen lugar para comenzar y los manuales de la ayuda de Vim `:help` tienen todas las referencias que vayas a poder necesitar.

Sin embargo, el usuario medio necesita algo más que lo que ofrece `vimtutor` y algo menos que el manual de `:help`. Esta guía trata de cerrar esa brecha destacando solo las funcionalidades más importante para aprender las partes más útiles de Vim en el menor tiempo posible.

Lo más probable es que no vayas a necesitar el 100% de las funcionalidades que ofrece Vim. Probablemente solo necesitarás saber el 20% de estas para convertirte en *Vimmer* destacado. Esta guía te enseñará cuales de las funcionalidades de Vim vas a encontrar más útiles.

Esta es una guía obstinada. Trata de técnica que utilizo habitualmente cuando uso Vim. La secuencia de los capítulos está pensada basandome en lo que tendría un sentido más lógico para un principiante a la hora de aprender Vim.

Esta guía está llena de ejemplos. Al aprender una nueva materia, los ejemplos son indispensables, el disponer de numerosos ejemplos hará que se fijen estos conceptos de una manera más efectiva.

Quiźas alguna persona se pregunten ¿por qué voy a necesitar aprender Vimscript? En mi primer año de uso de Vim, estaba satisfecho con solo saber utilizar Vim. A medida que pasó el tiempo y comencé a necesitar Vimscript más y más para escribir comandos personalizados para mis necesidades específicas a la hora de editar. Mientras estás dominando Vim, antes o después necesitarás aprender Vimscript. Así que ¿por qué no mejor cuanto antes? Vimscript es un lenguajes pequeño. Puedes aprender lo básico en solo cuatro capítulos de esta guía.

Puedes llegar lejos utilizando Vim sin conocer en absoluto Vimscript, pero conociéndolo te ayudará a sobresalir aún más.

Esta guía está escrita tanto para principiantes como para personas que utilicen Vim de una manera más avanzada. Comienza con conceptos amplios y simples y acaba con conceptos específicos y avanzados. Si ya crees que eres una persona con conocimientos avanzados, te recomendaría que igualmente leyeras esta guía desde el principio hasta el fin, porque ¡aprenderás algo nuevo!

## Cómo hacer la transición a Vim desde un editor de texto diferente

Aprender Vim es una experiencia satisfactoria, aunque dura. Hay dos enfoques principales a la hora de aprender Vim:

1. De un día para otro
2. Gradual

Hacerlo de un día para otro significa dejar de utilizar el IDE o editor que estuvieras utilizando y comenzar de inmediato a utilizar de manera exclisva Vim. La pega de este método es que tendrás una importante pérdida de productividad durante la primera o dos primeras semanas. Si eres un programador a tiempo completo, este método puede que no sea factible. Por esto es por lo que a la mayoría de personas, creo que la mejor manera de hacer la transición a Vim es utilizarlo de manera gradual.

Para utilizar Vim gradualmente, durante las primeras dos semanas, pasa una hora al día utilizando Vim como tu editor, mientras que el resto del tiempo puedes utilizar otros editores. Muchos editores modernos vienen con complementos de Vim. Cuando comencé, utilizaba un complemento popular de Vim para VSCode durante una hora al día. Gradualmente incrementé el tiempo con el complemento de Vim hasta que al final lo utilizaba durante todo el día. Ten en cuenta que estos complementos solo pueden emular una parte de las funcionalidades de Vim. Para experimentar toda la potencia de Vim como Vimscript, comamndos para la línea de comandos (Ex) y la integración con comandos externos, necesitarás utilizar el propio Vim.

Hubo dos momentos cruciales que me hicieron comenzar a utilizar Vim al 100%: cuando me enteré de que Vim tiene una estructura similar a la gramatical a la hora de ejecutar comandos (ver capítulo 4) y el complemento [fzf.vim](https://github.com/junegunn/fzf.vim) (ver capítulo 3).

El primero, cuando me di cuenta de la esctructura similar a la gramática de Vim, fue el momento definitivo en el que comprendí de lo que hablaban las personas que usaban Vim. No necesitaba aprender cientos de comandos únicos. Solo tenía que aprender un pequeño puñado de comandos y podría encadenarlos de una manera muy intuitiva para hacer muchas cosas.

El segundo, la posibilidad de ejecutar rápidamente una búsqueda de archivos de manera difusa era la funcionalidad de un IDE que más utilizaba. Cuando aprendí cómo hacerlo en Vim, gané un mayor impulso de velocidad y desde entonces nunca he vuelto a mirar atrás.

Cada persona programa de manera diferente. Sobre la introspección, encontrará que hay una o dos funcionalidades de tu editor o IDE favoritso que utilizas todo el tiempo. Quizás son la búsqueda difusa, saltar a una definición o una compilación rápida. Cualquiera que sea, identifícalas rápidamente y aprende cómo implementar esas en Evim (lo más probable es que Vim también pueda hacerlo). Tu velocidad a la hora de editar tendrá un gran impulso.

Una vez que puedas editar al 50% de velociad que lo hacías originalmente, es hora de pasarte por completo a Vim.

## Cómo leer esta guía

Esta es una guía práctica. Para llegar a dominar Vim necesitas desarrollar el músculo de tu memoria, no conocimiento intelectual.

No aprendes a montar en bicicleta leyendo una guía sobre cómo montar en bicicleta. Necesitas realmente montar en bicicleta.

Necesitas escribir cada comando que encontrarás en esta guía. No solo eso, necesitarás repetirlos varias veces y probar combinaciones diferentes. Busca que otras funcionalidades tiene el comando que acabas de aprender. El comando `:help` y un buscador de internet son tus mejores amigos. Tu meta no es conocer todo sobre un comando, si no ser capaz de jecutar ese comando con naturalidad y de manera instintiva.

Por mucho que haya tratado de moldear esta guía para ser lineal en su temática, algunos conceptos de esta guía tienen que ser presentados fuera de orden. Por ejemplo en el capítulo 1, menciono el comando de sustitución (`:s`), incluso aunque no trato sobre el hasta el capítulo 12. Para remediar esto, cada vez que un nuevo concepto que no se haya tratado todavía sea mencionado prematuramente, ofreceré una rápida guía de utilización sin una explicación detallada. Así que por favor, tengan paciencia conmigo :).

## Más ayuda

Aquí tienes un truco extra al utilizar el manual de la ayuda de Vim: supon que quieres aprender más sobre lo que hace `Ctrl-P` en el modo insertar. Si solo buscas `:h CTRL-P`, te enviará a lo que hace `Ctrl-P` en el modo normal.  Esa no es la ayuda sobre `Ctrl-P` que estabas buscando. En este caso, deberás buscar esto `:h i_CTRL-P`. El prefijo `i_` representa al modo insertar. Pon atención sobre a qué modo pertenece lo que andas buscando.

## Sintaxis

La mayoría de los comandos o frases relacionadas con código se mostrarán `de esta forma`.

Las cadenas de texto están rodeadas por un par de comillas dobles ("de esta forma").

Los comandos de Vim pueden ser abreviados. Por ejemplo, `:join` tiene un comando similar abreviado como `:j`. A lo largo de la guía, se utilizarán tanto las descripciones largas como cortas. Para los comandos que no son usados frecuentemente en esta guía, utilizaré la versión larga. Para los comandos que son utilizados frecuentemente, utilizaré la versión corta. Siento esta diversidad de uso. En general, cuando te encuentres con un comando nuevo, comprueba siempre en la ayuda de Vim para ver su forma abreviada

## Vimrc

En varios puntos de esta guía, me referiré a las opciones de *vimrc*. Si acabas de llegar a Vim, debes saber que *vimrc* es el archivo de configuración del editor.

No se tratará el tema de *vimrc* hasta el capítulo 21. Para aclarar un poco el tema, te mostraré brevemente cómo configurarlo.

Supongamos que necesitamos configurar las opciones de numeración de línea (`set number`). Si todavía no tienes un archivo *vimrc*, vamos a crear uno. Normalmente este archivo se ubica en la raíz de un directorio lammado `.vimrc` dentro de nuestro usuario del sistema. Dependiendo de tu sistema operativo, la ubicación puede ser diferente. En sistemas basados en Unix como GNU/Linux o macOS estará en `~/.vimrc`. Para ver donde deberías ubicar tu archivo, ehca un vistazo a `:h vimrc`.

Dentro del archivo añade una línea con lo siguiente `set number`. Guárdalo (`:w`) y después haz que Vim lo tenga en cuenta ejecutando `:source %`. Ahora deberías ver los números de línea mostrados en el margen izquierdo.

De manera alternativa, si no quieres realizar cambios en los ajustes que se guarden de forma permanentes, siempre puedes ejecutar el comando `set` en la línea de comandos, ejecutando `:set number`. La contrapartida de este método es que estos ajustes son temporales. Cuando cierres Vim los cambios y opciones desaparecen.

Ya que estamos aprendiendo sobre Vim y no sobre Vi, un ajuste que debes incluir es la opción `nocompatible`. Añade `set nocompatible` en tu archivo *vimrc*. Muchas funcionalidades específicas de Vim están inhabilitadas cuando está siendo ejecutado con la opción `compatible`.

En general, siempre que en la guía se mencione una opción de *vimrc*, simplemente añade esa opción en el archivo *vimrc*, guárdalo y haz que después Vim lo tenga en cuenta.

## Futuro, errores, preguntas

Llegarán más actualizaciones de la guía en el futuro. Si encuentras algún error o tienes alguna pregunta, por favor siéntete libre de ponerte en contacto conmigo.

También planeo más capítulos en futuras entregas, así que ¡permanece atento y atenta!

## Quiero más trucos sobre Vim

Para aprender más sobre Vim, puedes seguir en Twitter a [@learnvim](https://twitter.com/learnvim).
