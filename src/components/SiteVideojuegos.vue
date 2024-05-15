<template>
    <section class="videojuegos">
        <h2>VIDEOJUEGOS</h2>
        <div class="GroupElements">
            <article v-for="videojuego in videojuegos" :key="videojuego.id">
                <img :src="videojuego.imagenUrl" :alt="videojuego.nombre + ' Portada'">
                <h3>{{ videojuego.nombre }}</h3>
                <p>{{ videojuego.descripcion }}</p>
                <div class="diva">
                    <button @click="eliminarVideojuego(videojuego.id)">Eliminar</button>
                    <button @click="modificarVideojuego(videojuego)">Modificar</button>
                </div>
            </article>
        </div>
        
        <form v-if="videojuegoModificando" @submit.prevent="guardarModificacion">
            <label for="nombre">Nombre:</label>
            <input type="text" id="nombre" v-model="videojuegoModificado.nombre">
            <label for="descripcion">Descripción:</label>
            <input type="text" id="descripcion" v-model="videojuegoModificado.descripcion">
            <label for="imagenUrl">URL de la imagen:</label>
            <input type="text" id="imagenUrl" v-model="videojuegoModificado.imagenUrl">
            <button type="submit">Guardar</button>
        </form>

        <form v-else @submit.prevent="agregarVideojuego">
            <h3>AGREGAR NUEVO VIDEOJUEGO.</h3>
            <label for="nombreNuevo">Nombre:</label>
            <input type="text" id="nombreNuevo" v-model="nuevoVideojuego.nombre">
            <label for="descripcionNuevo">Descripción:</label>
            <input type="text" id="descripcionNuevo" v-model="nuevoVideojuego.descripcion">
            <label for="imagenUrlNuevo">URL de la imagen:</label>
            <input type="text" id="imagenUrlNuevo" v-model="nuevoVideojuego.imagenUrl">
            <button type="submit">Agregar</button>
        </form>
    </section>
</template>

<script>
export default {
    name: 'SiteVideojuegos',
    data() {
        return {
            videojuegos: [
                { id: 1, nombre: "Garry's Mod", descripcion: "Garry's Mod es un entorno que te permite jugar libremente con el motor físico...", imagenUrl: "https://i.ytimg.com/vi/od7LqmC2J5I/maxresdefault.jpg" },
            ],
            nuevoVideojuego: { nombre: '', descripcion: '', imagenUrl: '' },
            videojuegoModificando: null,
            videojuegoModificado: { id: null, nombre: '', descripcion: '', imagenUrl: '' }
        };
    },
    methods: {
        eliminarVideojuego(id) {
            this.videojuegos = this.videojuegos.filter(videojuego => videojuego.id !== id);
        },
        modificarVideojuego(videojuego) {
            this.videojuegoModificando = videojuego;
            this.videojuegoModificado.id = videojuego.id;
            this.videojuegoModificado.nombre = videojuego.nombre;
            this.videojuegoModificado.descripcion = videojuego.descripcion;
            this.videojuegoModificado.imagenUrl = videojuego.imagenUrl;
        },
        guardarModificacion() {
            const index = this.videojuegos.findIndex(videojuego => videojuego.id === this.videojuegoModificado.id);
            if (index !== -1) {
                this.videojuegos.splice(index, 1, this.videojuegoModificado);
            }
            this.videojuegoModificando = null;
            this.videojuegoModificado = { id: null, nombre: '', descripcion: '', imagenUrl: '' };
        },
        agregarVideojuego() {
            if (this.nuevoVideojuego.nombre && this.nuevoVideojuego.descripcion && this.nuevoVideojuego.imagenUrl) {
                const nuevoId = this.videojuegos.length + 1;
                const nuevoVideojuego = {
                    id: nuevoId,
                    nombre: this.nuevoVideojuego.nombre,
                    descripcion: this.nuevoVideojuego.descripcion,
                    imagenUrl: this.nuevoVideojuego.imagenUrl
                };
                this.videojuegos.push(nuevoVideojuego);
                this.nuevoVideojuego = { nombre: '', descripcion: '', imagenUrl: '' };
            }
        }
    }
};
</script>


<style scoped>
.videojuegos {

width: 100%;
    display: flex;
    flex-direction: column;
}

.GroupElements {
width: 100%;
display: flex;
justify-content: space-around;
flex-wrap: wrap;
}

article {
flex-direction: column;
display: flex;
width: 300px;
border-radius: 0.5rem;
margin-bottom: 1rem;
text-align: justify;
height: 500px;
color: white;

}

.videojuegos article {
border: 2px solid rgb(255, 255, 255);
}
.videojuegos h2{
    color: aliceblue;
    text-align: center;
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
    display: flex;
    flex-direction: column;
    padding: 10px;
    background-color: cadetblue;
    color: #000000;
    margin: 0.4rem;
    width: 100%;
    align-self: center;
    align-items: center;
}

form input{
    padding: 0.4rem;
    margin-bottom: 0.4rem;
    
    width: 90%;
}
form textarea{
    margin-top: 0.4rem;
    align-items: center;
}

@media (min-width: 360px){
    form input{
        width: 50%; 
    }
}
</style>