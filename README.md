## Inicializacion del proyecto

`npx create-react-app 2022netflix --template redux`

### Proceso de limpieza

### importar las librerias

material-ui/core, axios, firebase, react-router-dom, react-uuid, styled-components

### App.js - layout inicial

-creamos las rutas
-Renderizamos Login o el resto de App condicionado a la existencia de un usuario

## Estilos
-Utilizamos useStyles para crear una infraestructura que nos permita asignar estilos a cada uno de los componentes

## crear las carpetas de componentes : Pages

-creamos la infraestructura de los componentes que representan una pagina: Home, Login, Paypal, Profile, SignUp

### Estilos en los componentes de Pages

-Patron para anadir la infraestructura a todos los componentes pagina: Banner, Header, Plans, Row.

### Estilos en los componentes de la carpeta components

-creamos la infraestructura basica del resto de componentes

### Empezamos a trabajar en el componente header

- Importamos el logo
- Anadimos al AppBar una clases tranparent condicional, Esta clase se activa si la variable show = true.
- La variable show se convierte en true, cuando hacemos un scrool vertical de mas de 100px.
- Para escribir cuando el usuario hace un scroll vertical, anadimos un eventListener al objetio window.
- El eventListener esta activo una sola vez cada vez que refresquemos la pagina (useEffect con []).
- Una vez montado el componente, hay que limpiarlo para que no nos quede colgado el eventListener
- anadimos la rutas tanto al logo como al avatar

### comenzamos a trabajar en el componente Banner

- Hemos importado un pedazo de imagen como backgroundImage
- En React, tenemos que acompanar las backgroundImage con estilos como object-fit, background-size y background-position
- Hemos posiicionado el titulo de la peli, unos botenes y la descripcion
- como la descripcion viene de la API, tenemos que truncarla para asegurarnos de que nos cabe: Para ellosm hemos declarado la funcion truncate,
- Hemos anadido un div vacio, que oscurece la imagen hasta fusionarla con el resto del UI, que es oscuro

### Comenzamos a trabajar en el login
- Hemos creado un boton con styled components y le hemos llamado NetflixButton. Este boton esta totalmente customizado y podremos variar su longitud, color y otros estilos, pasandole props.
- Styled components para variar los estilos del input o del boton, pero para su posicionamiento le damos una clase normal.
- Hemos creado un input personalizado en styled components. Le hemos llamado NetflixInput. como InputBase era ya un componente de material ui, pues lo llamamos styled(InputBase). si hubiera sido un input de base styled.input``

### Componente profile
- Hemos trabajado en la distribucion
- <Plans>Texto</Plans>
- `const Plans = (children) => {return ()}`
- pasar props a tus styled components.
- en el caso de que el componente no sea binario, p.ej el tamanio sea pequenio, grande o mediano, entonces los solucionamos con una funcion y un switch

### Signup 

- Renderizado condicional, Hemos creado una variable signin.
- Si la variable es false, desplegamos el formulario.

### Proceso de registro y SignIn
- habilitado un cuenta en firebase
- inicializado el objeto auth
- capturado los datos tecleados por el usuario dentro del formulario
- registrado email y password con auth.create......
- signin con auth.signInWithEMail...

### Redux
- Habilitamos el slice userSlice para manejar el usuario en el componente que queramos.

### Persistencia
- Hemos anadido un "event listener" en App.js
- este event listener lo trae el objeto auth, escucha cada vez que cambia el usuario en firebase.
- Cada vez que cambia vuelve a inyectar el usuario en la capa de datos de userSlice(Redux)
- De esta manera recordamos que ya estamos detro aunque refresquemos la pagina.

### Requests
- Vamos a contruir el componente Row
- Hemos habilitado todos los endponint para acceder a themoviedb, y extraer los distintos objetos con toda la informacion clasificada por genero.