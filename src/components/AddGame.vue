<template>

        

    <form @submit.prevent="agregarVideojuego">
        <label for="nombre">Nombre:</label>
        <input type="text" id="nombre" v-model="nuevoVideojuego.nombre">
        <label for="descripcion">Descripción:</label>
        <input type="text" id="descripcion" v-model="nuevoVideojuego.descripcion">
        <label for="imagenUrl">URL de la imagen:</label>
        <input type="text" id="imagenUrl" v-model="nuevoVideojuego.imagenUrl">
        <button type="submit">Agregar</button>
    </form>
</template>


<script>
export default {
    name: 'AddGame',
    data() {
        return {
            nuevoVideojuego: { nombre: '', descripcion: '', imagenUrl: '' }
        };
    },
    methods: {
        agregarVideojuego() {
            if (this.nuevoVideojuego.nombre && this.nuevoVideojuego.descripcion && this.nuevoVideojuego.imagenUrl) {
                emit('addGame',this.nuevoVideojuego);
            }
        }

        //Falta el metodo de modificar y llamar a la funcion en el boton modificar
    }
};
</script>

<style scoped>
.videojuegos {

width: 100%;
}

.div {
width: 100%;
display: flex;
justify-content: space-around;
flex-wrap: wrap;
}

article {
flex-direction: column;
display: flex;
width: 30%;
border-radius: 0.5rem;
margin-bottom: 1rem;
text-align: justify;
height: 500px;
color: white;

}

.videojuegos article {
border: 2px solid rgb(255, 255, 255);
}

article h3 {
display: flex;
flex-wrap: nowrap;
margin-top: 0.5rem;
color: #d18624;

}

article img {
width: 100%;
border-radius: 0.5rem;
height: 200px;

}

article p {
display: flex;
flex-wrap: nowrap;
padding: 0.2rem;
}

.diva a {

width: 15%;
margin: 0.5rem;
background-color: #f0a020;
color: #000000;
float: right;
text-decoration: none;

}

.diva a:hover {
background: white;
}
form{
    padding: 10px;
    display: flex;
    flex-direction: column;
    color: white;
}

form input{
    padding: 0.4rem;
    margin-bottom: 0.4rem;
}
form textarea{
    margin-top: 0.4rem;
    align-items: center;
}
form button{

}

</style>