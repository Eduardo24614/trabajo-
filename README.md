[act-6.obj.js](https://github.com/user-attachments/files/32634229/act-6.obj.js)
//datos y medotos de un objeto
//ficha de menu
//los datos son distintos a proposito comparala forma
//datos y medotos de un objeto
//ficha de menu
//los datos son distintos a proposito comparala forma
const producto = {
    id:"p-07",
    nombre: "Agua de jamaica",
    precio: 15,
    categoria:"bebida",
    disponible: true,

   //metodos
   resumen(){
    return this.nombre + " - $ " + this.precio + "(" + this.categoria + ")"
   },

   estaDisponible(){
    return this.disponible;
   }
};

console.log("paso 1 _ imprimiendo el producto");
console.log(producto);

//paso 2 - Tres formas de leer
console.log("-----PASO 2 -----");
const campo = "nombre";
console.log(producto.nombre);
console.log(producto["nombre"]);
console.log(producto[campo]);

console.log("----- PASO 3 -----");
console.log(producto.resumen());
console.log(producto.estaDisponible());

// ----- PASO 4 usuario -----
const usuario = {
    id:"u-03",
    nombre:"juanito pistolas",
    correo:"juanito@cbtis258.edu.mx",
    telefono:1042364232,
    rol:"alumno"
};


// ----- PASO 5 -----
const pedido = {
    folio:"PR-0118",
    cliente: usuario,
    producto: producto,
    cantidad: 3,
    estado:"pendiente"
}


console.log("----- PASO 5 -----");
console.log(pedido.cliente.nombre);
console.log(pedido.producto.precio);
console.log(pedido.cliente.telefono);


// PASO 6 - desestructuracion
console.log("------ PASO 6 ------");
const {nombre, precio} = producto;
console.log(nombre, precio);

const {cantidad, nota = "sin nota"} = pedido;
console.log(cantidad, nota);
console.log("Eduardo Saul Fraire Baez")


//------ PASO 7 ------
const total = producto.precio * pedido.cantidad;
pedido.total = total;

console.log("-----PASO 7 -----");
console.log(pedido);

//------- PASO 8 COPIAR -------
console.log("------ PASO 8 -----")
const copiamala = producto;
copiamala.precio = 999;
console.log(producto.precio);
// VA IMPRIMIR 999 PORQUE ESO ES DE LA COPIAMALA Y PRODUCTO APUNTAN AL MISMO OBJETO
// la variable no guarda el objeto, guarda donde esta


producto.precio = 15;//la dejamos como estaba
const copiaBuena = {...producto};
copiaBuena.precio = 1000;
console.log(producto.precio);// 15 el original quedo intacto


//----- PASO 9 -----
console.log("----- PASO 9 -----")

const respuestaOK = {
    ok: true,
    data:pedido
};

const respuestaError = {
    ok: false,
    error: {
        mensaje:"elproducto no esta disponible",
        detalle:[]
    }
};


console.log(respuestaOK);
console.log(respuestaError);
