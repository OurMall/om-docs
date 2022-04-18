# Esquemas - Our Mall #

Los esquemas son un grupo de modelos y reglas que representan las entidades que contendra la base de datos de Our Mall, especificando tecnicamente como se relacionan entre si.

## Modelos ##

Los modelos representan cada coleccion a nivel teorico de la base de datos y los campos que contendra en su interior.

Formato:

```js
{
    field1: type
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
    gender: string, // M, F, O
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
    clients: Clients[]
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
    name: string,
    type: string, //Web, desktop, etc
    uri: string,
    contacts: string[],
    logo_uri: string,
    policy_uri: string,
    terms_uri: string
    redirect_uris: string[],
    is_disabled: boolean,
    created_at: number
}
```

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
    owner_id: string, //User
    categorie_id: string, //Categorie
    tags: string[],
    services: Services[],
    suscribers: Users[],
    products: Products[],
    created_at: number
}
```

- **owner_id:** Usuario propietario del espacio de trabajo.  
- **categorie_id:** Id de la categoria a la que hace parte el espacio de trabajo.  
- **services:** Servicios con los que cuenta el espacio de trabajo.  
- **members:** Miembros que hacen parte del espacio de trabajo.  
- **created_at:** Fecha o estampa de tiempo en el que se creo el espacio de trabajo.  

### Workspaces Profiles - workspaces_profiles ###

```js
{
    _id: string,
    workspace_id: string, // Workspace
    name: string,
    description: string,
    slogan: string,
    logo: string,
    background_color: string,
    images: string[], // photos, pictures
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
}
```

### Invoices - invoices ###

```js
{
    _id: string,
    user_id: string,
    product_id: 
}
```

### Invoices Details - Invoices ###

```js
{

}
```

### System Cash - system_cash ###

```js
{
    field: type,
}
```

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

### Rooms - rooms ###

```js
{
    _id: string,
    owner_id: string, // User
    name: string,
    description: string,
    is_disabled: boolean,
    capacity: number,
    created_at: number
}
```

### Rooms Details - rooms_details ###

```js
{
    _id: string,
    room_id: string, // Room
    user_id: string, // User
    message: string,
    timestamp: number
}
```
