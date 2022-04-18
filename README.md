# Our Mall #

Our Mall es un aplicativo que busca simular un centro comercial virtual, que tiene como objetivo brindar a sus usuarios la posibilidad de que puedan implementar o asociar sus comercios al sistema y de esta forma adquirir clientes que visiten o se suscriban a uno/unos espacio/s de trabajo.

Tabla de contenido

- [Our Mall](#our-mall)
  - [Propósito e idea principal](#propósito-e-idea-principal)
    - [Funcionalidades](#funcionalidades)
    - [Observaciones](#observaciones)
  - [Metricas de desarrollo](#metricas-de-desarrollo)
  - [Equipo de desarrollo](#equipo-de-desarrollo)
  - [Documentos de desarrollo](#documentos-de-desarrollo)

## [Propósito e idea principal](#purpose) ##

La idea principal de Our Mall se centra en representar un Centro Comercial virtual, espacio en el cual un usuario podrá seleccionar un rol que emplee en su ámbito laboral al registrarse en la plataforma, ya sea vendedor y/o cliente. En caso de ser vendedor, podrá crear un espacio de trabajo (el cuál analógicamente representaría un negocio) y adquirir o implementar 4 funciones principales: gestion de caja, venta en linea, anuncios y notificaciones e inventario de productos. Por otra parte, si el usuario elije el rol de cliente podrá visitar los diferentes espacios de trabajo que hay disponibles en la plataforma además de consumir los servicios que ofrezcan los mismos.

### [Funcionalidades](#funcionalidades) ###

Las funcionalidades principales que tendrán a disposición los vendedores se describen a continuación:

1. **Vitrina de productos:** productos disponibles por cada espacio, estadísticas relacionadas a los productos (stock, ofertas, cantidad de productos y calificación de productos).
2. **Sistema de caja:** gestion de finanzas y ventas realizadas, estadísticas relacionadas con las ganancias de cada vendedor en su espacio de trabajo, generación de facturas.
3. **Anuncios & notificaciones:** relacionados a los productos o los servicios que el vendedor disponga, a los cuales el cliente podrá suscribirse y ver al visitar el espacio de trabajo.
4. **Integración de pagos:** por cada espacio de trabajo, en el cual el vendedor podrá ofrecer ventas de la vitrina de productos y podrá recibir pagos por dichos elementos.

---

Las funcionalidades principales que tendrán a disposición los clientes se describen a continuación:

1. **Busqueda & filtro de espacios de trabajo:** buscar y filtrar los espacios de trabajo disponibles en el aplicativo, ordenamiento por categorias.
2. **Visitar espacios de trabajo:** visualizar e interactuar con los espacios de trabajo disponibles.
3. **Suscripciones:** asociar cuenta, suscripción de notificaciones por cada espacio de trabajo.
4. **Consumo de servicios:** acceso a los servicios que ofrece los espacios de trabajo, compra en línea de productos.

### [Observaciones](#notes) ###

- Los servicios ofrecidos por la plataforma son 100% gratis.
- No es necesario el registro del usuario para consumir parte de las funcionalidades que ofrecemos, como visualizar los espacios de trabajo creados.
- Para poder registrar un espacio de trabajo, se tendran en cuenta ciertas validaciones para verificar que el usuario en cuestión es mayor de edad.
- No podrán haber espacios de trabajo que se dedicen al comercio de elementos ilegales como: armas, drogas, etc.
- Nos reservamos el derecho de cerrar un espacio de trabajo en caso de no cumplir con las normativas establecidas.
- Restringimos la creacion de espacios de trabajo a solo uno (1) por usuario, de esta forma se evita el monopolio.
- La creacion de multiples cuentas para crear espacios de trabajo asociados puede ser motivo de bloqueo para el usuario y los espacios de trabajo infiltrados.

## [Metricas de desarrollo](#metricas-de-desarrollo) ##

Las metricas de desarrollo expresan las reglas semanticas a nivel de codigo y documentos que deberan seguir los desarrolladores para un correcto manejo de los estandares de calidad y buenas practicas.

A continuación se declaran las métricas a tener en cuenta una vez se comience con el desarrollo del proyecto, estás a su vez, irán regidas por ciertas reglas y estándares de código, entre otros.

> "Diga lo que piense, piense lo que diga."

1. A nivel de codigo
   1. Absolutamente todas las lineas de codigo deberan estar escritas en ingles.
   2. Las clases deberan ser **sustantivos**, de ninguna forma deberian representar verbos. Por ejemplo:

      ```py
         class Person # Si, es un sustantivo.
         class Walk # No, es un verbo.
      ```

   3. Las funciones y métodos deberán representar **verbos**, ya que abstractamente representan acciones. Por ejemplo:

      ```py
         def walk() #Si, es un verbo.
         def person() #No, es un sustantivo.
      ```

   4. Redaccion...
2. Gestion de codigo fuente (git)
   1. Cada integrante del equipo de desarrollo debera crear su rama siguiendo la notacion a continuacion:

      ```git
         develop/<developer-name> # Notacion.
         develop/brian # Ejemplo.
         git branch develop/brian # Creariamos una rama con nuestros nombre.
      ```

   2. Al realizar los commits se debe indicar en los comentarios de cada uno, que acción se realizo a nivel de código. Por ejemplo:

      ```git
         "Add: person class in the DB model. BC" 
         # El Add representa la accion, lo seguido es lo que se realizo y por ultimo,
         # Las iniciales del desarrollador que realizo la accion
         git commit -m "Add: user schema in the DB context. BC" # Ejemplo.
      ```

   3. Redaccion...
3. A nivel de documentacion
   1. La máxima puntuación o rango de puntos para una historia de usuario será de entre 0 y 20 como máximo.
4. Redaccion...

## [Equipo de desarrollo](#equipo-de-desarrollo) ##

El equipo de desarrollo representa los miembros que se haran cargo de sacar adelante el proyecto de Our Mall, se listan a continuacion:

1. [Brian Castro Bedoya](https://github.com/briancastro-bc)
2. [Anderson Méndez Marín](https://github.com/anderson735)
3. [Santiago Arias Mosquera](https://github.com/santiagoAM2004)
4. [Juan Jose Naranjo](https://github.com/Naranjo17)
5. [Sergio Alejandro Cardona](https://github.com/sergiocardona2004)

## [Documentos de desarrollo](#documentos-de-desarrollo) ##

- [Requisitos](./REQUIREMENTS.md)
- [Historias de usuarios](./USER-STORIES.md)
