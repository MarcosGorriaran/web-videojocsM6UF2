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
           {{ console.log(videojuegoModificado) }}
            <label for="nombre">Nombre:</label>
            <input type="text" id="nombre" v-model="videojuegoModificado.nombre">
            <label for="descripcion">Descripción:</label>
            <input type="text" id="descripcion" v-model="videojuegoModificado.descripcion">
            <InputFile :file="videojuegoModificado.imagenUrl" @fileChange="FileChangeHandlerUpdateGame"></InputFile>
            <button type="submit">Guardar</button>
        </form>

        <form v-else @submit.prevent="agregarVideojuego">
            <h3>AGREGAR NUEVO VIDEOJUEGO.</h3>
            <label for="nombreNuevo">Nombre:</label>
            <input type="text" id="nombreNuevo" v-model="nuevoVideojuego.nombre">
            <label for="descripcionNuevo">Descripción:</label>
            <input type="text" id="descripcionNuevo" v-model="nuevoVideojuego.descripcion">
            <label>Image</label>
            <InputFile :file="nuevoVideojuego.imagenUrl" @fileChange="FileChangeHandlerNewGame"></InputFile>
            <button type="submit">Agregar</button>
        </form>
    </section>
</template>

<script>
import InputFile from './InputFile.vue';
export default {
    name: 'SiteVideojuegos',
    data() {
        return {
            gameStorageKey: "Videogames",
            videojuegos: [],
            nuevoVideojuego: { nombre: '', descripcion: '', imagenUrl: null},
            videojuegoModificando: null,
            videojuegoModificado: { id: null, nombre: '', descripcion: '', imagenUrl:''},
            example: null, image: false, preview: null
        };
    },
    components:{
        InputFile
    },
    methods: {
        eliminarVideojuego(id) {
            this.videojuegos = this.videojuegos.filter(videojuego => videojuego.id !== id);
            this.UpdateLocalStorage();
        },
        modificarVideojuego(videojuego) {
            this.videojuegoModificando = videojuego;
            this.videojuegoModificado.id = videojuego.id;
            this.videojuegoModificado.nombre = videojuego.nombre;
            this.videojuegoModificado.descripcion = videojuego.descripcion;
            this.videojuegoModificado.imagenUrl = videojuego.imagenUrl;
            this.UpdateLocalStorage();
        },
        guardarModificacion() {
            const index = this.videojuegos.findIndex(videojuego => videojuego.id === this.videojuegoModificado.id);
            if (index !== -1) {
                this.videojuegos.splice(index, 1, this.videojuegoModificado);
            }
            this.videojuegoModificando = null;
            this.videojuegoModificado = { id: null, nombre: '', descripcion: ''};
        },
        agregarVideojuego() {
            if (this.nuevoVideojuego.nombre && this.nuevoVideojuego.descripcion && this.nuevoVideojuego.imagenUrl) {
                let nuevoId
                try{
                    nuevoId = this.videojuegos.length + 1;
                }catch{
                    nuevoId = 1;
                }
                
                const nuevoVideojuego = {
                    id: nuevoId,
                    nombre: this.nuevoVideojuego.nombre,
                    descripcion: this.nuevoVideojuego.descripcion,
                    imagenUrl: this.nuevoVideojuego.imagenUrl
                };
                console.log(this.videojuegos);
                this.videojuegos.push(nuevoVideojuego);
                this.nuevoVideojuego = { nombre: '', descripcion: '', imagenUrl: '' };
                this.UpdateLocalStorage();
            }
        },
        UpdateLocalStorage(){
            localStorage.setItem(this.gameStorageKey,JSON.stringify(this.videojuegos))
        },
        LoadLocalStorage(){
            let data = localStorage.getItem(this.gameStorageKey);
            if(data === null){
                this.videojuegos = [];
            }else{
                this.videojuegos = JSON.parse(data);
            }
        },
        FileChangeHandlerNewGame(callback){
            this.nuevoVideojuego.imagenUrl=callback;
        },
        FileChangeHandlerUpdateGame(callback){
            this.videojuegoModificado.imagenUrl=callback;
        }
    },
    beforeMount(){
        console.log("load");
        this.LoadLocalStorage();
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