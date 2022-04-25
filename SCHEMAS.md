# Esquemas - Our Mall #

Los esquemas son un grupo de modelos y reglas que representan las entidades que contendra la base de datos de Our Mall, especificando tecnicamente como se relacionan entre si.

## Modelos ##

Los modelos representan cada coleccion a nivel teorico de la base de datos y los campos que contendra en su interior.

Formato:

```js
{
    field1: type,
    field2: type,
    field3: type,
    field4: type
}
```

---

### Users - users ###

```js
{
    _id: string,
    name: string,
    given_name: string,
    family_name: string,
    middle_name: string,
    nickname: string,
    preferred_username: string,
    gender: string,
    email: string,
    password: string,
    phone_number: string,
    birthdate: string,
    zoneinfo: string,
    locale: string,
    email_verified: boolean,
    phone_number_verified: boolean,
    is_blocked: boolean,
    is_disabled: boolean,
    created_at: number,
    updated_at: number,
    permissions: Permissions[],
    groups: Groups[],
    clients: Clients[],
    favorites: Products[]
}
```

- **name:** Nombre completo del usuario  
- **given_name:** Nombre principal o primer nombre del usuario. Nota: en algunas culturas una persona puede tener multiples nombres principales.  
- **family_name:** Apellido del usuario. Nota: en algunas culturas una persona puede tener multiples apellidos.  
- **middle_name:** Nombre secundario o segundo nombre del usuario.  
- **nickname:** Apodo o nombre abreviado del usuario.  
- **preferred_username:** Nombre corto con el que el usuario se identifica mejor.  
- **gender:** Genero del usuario entre masculino (male) o femenino (male). Otros valores pueden ser utilizados.  
- **email:** Correo electronico del usuario  
- **password:** Contrasena asociada a la cuenta del usuario.  
- **phone_number:** Numero de celular del usuario.  
- **birthdate:** Fecha de nacimiento del usuario.  
- **zoneinfo:** Zona horaria del usuario. Por ejemplo: Europe/Paris, America/Bogota
- **locale:** Etiqueta del lenguaje local del usuario. Por ejemplo: en-US, es-ES.
- **email_verified:** Estado del correo electronico del usuario.  
- **phone_number_verified:** Estado del numero de celular del usuario.  
- **is_blocked:** Estado legal en la plataforma del usuario.  
- **is_disabled:** Estado de la cuenta del usuario.  
- **created_at:** Fecha de creacion de la cuenta del usuario.  
- **updated_at:** Ultima fecha de actualizacion de la cuenta del usuario.  
- **permissions:** Permisos que posee el usuario.  
- **groups:** Grupos a los que hace parte el usuario.  
- **clients:** Clientes registrados para la comunicacion de la API por el usuario.
- **favorites:** Lista de productos favoritos que tiene el usuario.

### Users Profiles - users_profiles ###

```js
{
    _id: string,
    user_id: string,
    picture: string,
    website: string,
    biography: string,
    address: {
        formatted: string,
        street_address: string,
        locality: string,
        region: string,
        postal_code: string,
        country: string
    }
}
```

- **user_id:** Identificador unico del propietario del perfil.  
- **picture:** Foto o imagen del usuario.  
- **website:** Sitio web o red social del usuario.  
- **biography:** Biografia o descripcion breve del usuario.  
- **address:** Direccion o datos de la direccion fisica del usuario:  
  - **formatted:** Todos los datos de la direccion formateados en una sola cadena.
  - **street_address:** Nombre de la calle, numero, apartamento, piso.  
  - **locality:** Ciudad local o componente local del usuario. Por ejemplo: Armenia.  
  - **region:** Estado, departamento, provincia del usuario. Por ejemplo: Quindio.  
  - **postal_code:** Codigo unico e identificador de la zona donde se encuentra el usuario. Por ejemplo: 630002.  
  - **country:** Pais del usuario.  

### Clients - clients ###

```js
{
    _id: string,
    user_id: string,
    client_id: string,
    client_secret: string,
    redirect_uris: string[],
    response_types: string[],
    grant_types: string[],
    application_type: string,
    contact: string,
    client_name: string,
    logo_uri: string,
    client_uri: string,
    policy_uri: string,
    tos_uri: string,
    jwks_uri: string,
    subject_type: string,
    default_max_age: number,
    is_disabled: boolean,
    created_at: number
}
```

- **user_id:** Usuario/desarrollador propietario del cliente/aplicacion.
- **client_id:** Identificador unico generado por la plataforma con el cual las aplicaciones se identificaran para la autorizacion.
- **client_secret:** Pareja identificadora del **client_id**, representa una especie de "contrase&ntilde;a" para el cliente
- **redirect_uris:** Lista de URI's para el redireccionamiento una vez se complete la autorizacion.
- **response_types:** El tipo de respuesta que espera recibir el cliente. Por ahora se implementa &uacute;nicamente `code`
- **grant_types:** El tipo de flujo al que se le autoriza acceder al cliente. Inicialmente solo se implementa `authorization_code`
- **application_type:** El tipo de aplicaci&oacute;n que desea implementar la autenticacion. Se definen unicamente dos `native` & `web`
- **contact:** Email de contacto de la organizacion/usuario due&ntilde;o de la aplicaci&oacute;n.
- **client_name:** Nombre oficial del cliente que desea consumir los servicios.
- **logo_uri:** URI del alojamiento del logotipo de la aplicaci&oacute;n
- **client_uri:** URI del dominio oficial de la aplicaci&oacute;n. No puede contener fragmentos, parametros de consulta ni algo por el estilo.
- **policy_uri:** URI de las politicas que ofrece el cliente consumidor.
- **tos_uri:** URI de los terminos del servicio que ofrece el cliente consumidor.
- **jwks_uri:** URL del documento para el conjunto de JSON Web Key que maneja el cliente.
- **subject_type:** Tipo de cliente dependiendo de como es capaz de manejar sus credenciales. Se definen dos tipos `confidential/pairwise` & `public`
- **default_max_age:** Tiempo por defecto que durar&aacute; la autenticaci&oacute;n. Se establece por defecto 10 d&iacute;as
- **is_disabled:** Estado en el que se encuentra el cliente.
- **created_at:** Fecha de creaci&oacute;n estampado en el cual se creo el cliente.

### Tokens - tokens ###

```js
{
    _id: string,

    is_revoke: boolean,
    updated_at: number,
    created_at: number
}
```

### Permissions - permissions ###

```js
{
    _id: string,
    code_name: string,
    name: string, 
    description: string 
}
```

- **code_name:** Nombre clave del permiso. sell, buy, block  
- **name:** Nombre representativo del permiso. Por ejemplo: Vender, Comprar, Bloquear.  
- **description:** Descripcion relacionada al permiso.  

### Groups - groups ###

```js
{
    _id: string,
    code_name: string,
    name: string, 
    description: string,
    permissions: Permissions[]
}
```

- **code_name:** Nombre clave del grupo.  
- **name:** Nombre representativo del grupo. Por ejemplo: Cliente, Adminstrador, Vendedor.  
- **description:** Descripcion relacionada al grupo.  
- **permissions:** Permisos que tendra un grupo.  

### Categories - categories ###

```js
{
    _id: string,
    name: string,
    description: string,
    created_at: number
}
```

- **name:** Nombre de la categoria.  
- **description:** Descripcion de la categoria.  
- **created_at:** Fecha de creacion de la categoria.  

### Workspaces - workspaces ###

```js
{
    _id: string,
    owner_id: string,
    categorie_id: string,
    tags: string[],
    services: Services[],
    suscribers: Users[],
    products: Products[],
    notifications: Notifications[],
    created_at: number
}
```

- **owner_id:** Usuario propietario del espacio de trabajo.  
- **categorie_id:** Id de la categoria a la que hace parte el espacio de trabajo.
- **tags:** Etiquetas asociadas al espacio de trabajo. Por ejemplo: ropa-de-marca, vestidos, mujer, hombre, etc.
- **services:** Lista de servicios habilitados con los que cuenta el espacio de trabajo.  
- **suscribers:** Lista de miembros que hacen parte del espacio de trabajo o se han suscrito.
- **products:** Lista de productos que hacen parte del espacio de trabajo.
- **notifications:** Lista de notificaciones que posee el espacio de trabajo.
- **created_at:** Fecha o estampa de tiempo en el que se creo el espacio de trabajo.  

### Workspaces Profiles - workspaces_profiles ###

```js
{
    _id: string,
    workspace_id: string,
    name: string,
    description: string,
    slogan: string,
    logo: string,
    background_color: string,
    images: string[], 
    social_media: string[],
    address: {
        formatted: string,
        street_address: string,
        locality: string,
        region: string,
        postal_code: string,
        country: string
    },
}
```

- **workspace_id:** Identificador unico referenciado por el espacio de trabajo al cual le pertenece el perfil.  
- **name:** Nombre del espacio de trabajo.  
- **description:** Descripcion/Detalles del espacio de trabajo.  
- **slogan:** Lema o frase celebre del espacio de trabajo.  
- **logo:** Imagen del logo del espacio de trabajo.  
- **images:** Imagenes/Galleria del espacio de trabajo en caso de tener espacio fisico.  
- **background_color:** Color de fondo del espacio de trabajo.  
- **social_media:** Lista de redes sociales que puede asociar al espacio de trabajo.  
- **address:** Direccion fisica del espacio de trabajo:  
  - **formated:** Direccion general formateada en una sola cadena.  
  - **street_address:** Local, negocio, calle del espacio de trabajo.  
  - **locality:** Ciudad donde esta ubicado el espacio de trabajo.  
  - **region:** Departamento, provincia, estado del espacio de trabajo.
  - **postal_code:** Codigo postal de la zona del espacio de trabajo.  
  - **country:** Pais del espacio de trabajo.  

### Services - services ###

```js
{
    _id: string,
    name: string,
    activate: boolean
}
```

- **name:** Nombre del servicio que va a poder integrar el espacio de trabajo.
- **activate:** Estado del espacio

### Products - products ###

```js
{
    _id: string,
    workspace_id: string,
    name: string,
    detail: string,
    price: {
        value: number,
        currency: string
    },
    vat: number,
    stock: number,
    images: string[],
    status: string,
    is_available: boolean,
    questions: Questions[],
    created_at: number
}
```

- **workspace_id:** Espacio de trabajo al que se asocia el producto.
- **name:** Nombre o titulo del prodcuto
- **detail:** Detalle extenso para cada producto
- **price:** Detalles del precio del producto
  - **value:** Valor del precio del producto
  - **currency:** Moneda del valor del producto
- **vat:** IVA relacionado al producto
- **stock:** Cantidad disponible del producto.
- **images:** Lista de imagenes relacionadas del producto
- **status:** En que estado se encuentra el producto. Por ejemplo: nuevo, usado, reacondicionado.
- **is_available:** Disponibilidad del producto: Por ejemplo: disponible o no disponible.
- **questions**: Lista de preguntas realizadas para el producto
- **created_at:** Fecha de creacion para cada producto

### Questions - questions ###

```js
{
    _id: string,
    product_id: string,
    user_id: string,
    value: string,
    responses: Responses[
        {
            _id: string,
            value: string,
            timestamp: number
        }
    ],
    created_at: number
}
```

- **product_id:** Producto al que hace parte la pregunta.
- **user_id:** Usuario que realizo la pregunta
- **value:** Escrito o valor textual de la pregunta.
- **responses:** Lista de respuestas de la pregunta.
  - **value:** Escrito o valor textual de la respuesta.
  - **timestamp:** Estampa de tiempo en el que se realizo la respuesta.
- **created_at:** Fecha de creacion de la pregunta.

### Invoices - invoices ###

```js
{
    _id: string,
    code: string,
    user_id: string,
    workspace_id: string,
    invoices_details: InvoicesDetails[],
    payment_method: {
        name: string,
        type: string, 
        currency: string
    },
    total_vat: number,
    total_price: number,
    total_amount: number,
    date: number,
    created_at: number,
}
```

- **code:** Codigo generado de la factura
- **user_id:** Usuario propietario o al cual se le efectiva la factura.
- **workspace_id:** Espacio de trabajo al que hace parte la factura.
- **invoices_details:** Lista de los detalles de la factura en los cuales se encuentran el o los productos transaccionados.
- **payment_method:** Conjunto del metodo de pago
  - **name:** Nombre del tipo de pago. Por ejemplo: efectivo, tarjeta
- **total_vat:** Valor total del iva
- **total_price:** Precio total sin IVA
- **total_amout:** Costo total con el IVA incluido
- **date:** Fecha en la cual se transacciona la factura.
- **created_at:** Fecha en la cual se crea la factura.

### Invoices Details - Invoices ###

```js
{
    _id: string,
    invoice_id: string,
    product_id: string,
    number: number,
}
```

- **invoice_id:** Factura a la cual pertenecen los detalles
- **product_id:** ID del proyecto que se facturo
- **number:** Cantidad de productos que se asociaron a la factura.

### Cash Register - cash_register ###

```js
{
    _id: string,
    workspace_id: string,
    cash_register_details: CashRegisterDetails[],
    accumulate: number,
}
```

- **workspace_id:** Espacio de trabajo al que pertenece la caja de registro
- **cash_register_details:** Lista de detalles de la caja de registro.
- **accumulate:** Dinero acumulado por cada transaccion con el sistema de caja.

### Cash Registers Details - cash_register_details ###

```js
{
    _id: string,
    cash_register: string,
    product_id: string,
    number: number,
    registered_at: number
}
```

- **cash_register:** Caja registradora a la que pertenecen los detalles.
- **product_id:** Producto asociado al detalle de la caja registradora.
- **number:** Numero de productos asociado al espacio de trabajo.
- **registered_at:** Fecha en la que se hizo el registro de la caja.

### Notifications - notifications ###

```js
{
    _id: string,
    title: string,
    image: string,
    link: string,
    description: string,
    is_active: boolean,
    created_at: number,
    expired_at: number
}
```

- **title:** Titulo o nombre de la notificacion
- **image:** Imagen representativa que decora la notificacion
- **link:** Enlace a donde redigira la notificacion.
- **description:** Breve descripcion relacionada en que se basa la notificacion.
- **is_active:** Estado de la notificacion
- **created_at:** Fecha en la que se creo la notificacion
- **expired_at:** Fecha de vigencia de la notificacion

### Rooms - rooms ###

```js
{
    _id: string,
    owner_id: string,
    room_details: RoomDetails[],
    name: string,
    description: string,
    is_disabled: boolean,
    capacity: number,
    created_at: number
}
```

- **owner_id:** Usuario creador de la sala de soporte.
- **name:** Nombre de la sala de soporte
- **description:** Descripcion breve relacionada a la sala de soporte
- **is_disabled:** Estado de la sala de soporte
- **capacity:** Capacidad de usuarios de la sala de soporte
- **created_at:** Fecha de creacion de la sala de soporte

### Rooms Details - rooms_details ###

```js
{
    _id: string,
    room_id: string,
    user_id: string,
    message: string,
    timestamp: number
}
```

- **room_id:** Sala de soporte a la que hacen parte los detalles.
- **user_id:** Usuario que interactua con la sala de soporte.
- **message:** Mensaje enviado por el usuario a la sala de soporte.
- **timestamp:** Estampa de tiempo en el que se envio el mensaje.

### Tickets - tickets ###

```js
{

}
```
