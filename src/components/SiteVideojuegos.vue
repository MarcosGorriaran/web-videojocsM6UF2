<template>
    <section class="videojuegos">
        
        <h2>VIDEOJUEGOS</h2>
        <div class="div">
            <article v-for="videojuego in videojuegos" :key="videojuego.id">
                <img :src="videojuego.imagenUrl" :alt="videojuego.nombre + ' Portada'">
                <h3>{{ videojuego.nombre }}</h3>
                <p>{{ videojuego.descripcion }}</p>
                <div class="diva">
                    <button @click="eliminarVideojuego(videojuego.id)">Eliminar</button>
                    <button @click="eliminarVideojuego(videojuego.id)">Modificar</button>
                </div>
            </article>
        </div>
        
    </section>
</template>


<script>
import AddGame from 'AddGame.vue'
export default {
    name: 'SiteVideojuegos',
    data() {
        return {
            videojuegos: [
                { id: 1, nombre: "Garry's Mod", descripcion: "Garry's Mod es un entorno que te permite jugar libremente con el motor físico...", imagenUrl: "@/assets/juego1.jpg" }
                //   { id: 2, nombre: "The Binding Of Isaac", descripcion: "Cuando la madre de Isaac empieza a escuchar la voz de Dios exigiéndole un sacrificio...", imagen: "@/assets/juego2.jpg" },
            ],
            nuevoVideojuego: { nombre: '', descripcion: '', imagenUrl: '' }
        };
    },
    methods: {
        eliminarVideojuego(id) {
            this.videojuegos = this.videojuegos.filter(videojuego => videojuego.id !== id);
        },
        agregarVideojuego() {
            if (this.nuevoVideojuego.nombre && this.nuevoVideojuego.descripcion && this.nuevoVideojuego.imagenUrl) {
                const nuevoId = this.videojuegos.length + 1;
                const nuevoVideojuego = {
                    id: nuevoId,
                    nombre: this.nuevoVideojuego.nombre,
                    descripcion: this.nuevoVideojuego.descripcion,
                    imagen: this.nuevoVideojuego.imagenUrl
                };
                this.videojuegos.push(nuevoVideojuego);
                this.nuevoVideojuego = { nombre: '', descripcion: '', imagenUrl: '' };
                
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