# Our Mall #

Our Mall es un aplicativo que busca simular un centro comercial virtual, que tiene como objetivo brindar a sus usuarios la posibilidad de que puedan implementar o asociar sus comercios al sistema y de esta forma adquirir clientes que visiten o se suscriban a uno/unos espacio/s de trabajo.

## Topics ##

1. [Propósito e idea](#purpose)
2. [Funcionalidades](#funcionallity)
3. [Requisitos](./REQUIREMENTS.md)
   1. Roles del aplicativo
   2. Requisitos funcionales
   3. Requisitos no funcionales
4. [Historias de usuario](./USER-STORIES.md)
5. [Modelado de la base de datos](./MODELS.md)
6. [Observaciones](#notes)

### [Propósito e idea principal](#purpose) ###

La idea principal de Our Mall se centra en representar un Centro Comercial virtual, espacio en el cual un usuario podrá seleccionar un rol que emplee en su ámbito laboral al registrarse en la plataforma, ya sea vendedor y/o cliente. En caso de ser vendedor, podrá crear un espacio de trabajo (el cuál analógicamente representaría un negocio) y adquirir o implementar 4 funciones principales: gestion de caja, venta en linea, anuncios y notificaciones e inventario de productos. Por otra parte, si el usuario elije el rol de cliente podrá visitar los diferentes espacios de trabajo que hay disponibles en la plataforma además de consumir los servicios que ofrezcan los mismos.

### [Funcionalidades](#funcionallity) ###

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
