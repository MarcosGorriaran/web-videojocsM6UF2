<template>
    <section class="cajanot">
        <h2>NOTICIAS</h2>
        <div class="noticias">
            <article class="notart">
                <h3>Los videojuegos como herramientas para el
                    conocimiento</h3>
                <p>Desde que comenzamos nuestra andadura con GammeraNest y como
                    equipo creativo, hace ya diez años, asesorando a museos y otras
                    compañías sobre cómo usar la narrativa de los videojuegos a su
                    favor, siempre hemos pensado que el conocimiento debe ser
                    compartido con todos si queremos que este mundo sea mejor y que
                    la única forma de adquirirlo es trabajando duro y aprendiendo
                    para posteriormente poder transmitirlo.</p>
                <img src="@/assets/noticia1.jpg" alt="Noticia 1">
                <div class="divnot">
                    <a href="#">Seguir la noticia</a>
                </div>
            </article>
            <article class="notart">
                <h3>Eventos y Pruebas de los Dioses en Assassin's Creed Origins</h3>
                <p>Las Pruebas de los Dioses son una serie de combates especiales que tienen lugar contra varios dioses
                    del antiguo Egipto. Estos combates están disponibles de forma temporal. Es decir, sólo podrás
                    enfrentarte al dios en cuestión durante un tiempo determinado, que es una semana. Por el momento no
                    se ha aclarado si los enemigos que ya han aparecido volverán a estar disponibles más adelante.
                    Aclararemos esta información cuando Ubisoft se pronuncie al respecto.</p>
                <img src="@/assets/noticia2.jpg" alt="Noticia 2">
                <div class="divnot">
                    <a href="noticia.html">Seguir la noticia</a>
                </div>
            </article>
            <article class="notart">
                <h3>Nuevas pistas sugieren que el nuevo juego de HideoKojima esDeath Stranding 2</h3>
                <p>A pesar de que sus títulos suelen generar opiniones divididas,
                    Kojima Productions es una de las desarrolladoras que más dan de
                    qué hablar. Aunque la compañía aún no ha revelado oficialmente su
                    próximo proyecto, con crípticos mensajes su jefe, Hideo Kojima,
                    ha estado emocionando a los fans sobre una pronta revelación y
                    las sospechas sobre Death Stranding se hacen más grandes.</p>
                <img src="@/assets/noticia3.jpeg" alt="Noticia 3" height="35%">
                <div class="divnot">
                    <a href="#">Seguir la noticia</a>
                </div>
            </article>
            <article class="notart">
                <h3>4.000 dólares por doblar un juego millonario:'Bayonetta 3' es el último escándalo</h3>
                <p>El próximo 28 de octubre PlatinumGames lanza 'Bayonetta 3', uno
                    de los juegos más esperados para la Nintendo Switch. El título es
                    prometedor, pero su lanzamiento se ha convertido en un verdadero
                    escándalo. Una actriz de doblaje ha puesto el grito en el cielo
                    por un tema siempre sensible: según ella ofrecen sueldos
                    miserables incluso en producciones que acaban generando millones
                    y millones de dólares.</p>
                <img src="@/assets/noticia4.jpeg" alt="Noticia 4">
                <div class="divnot">
                    <a href="#">Seguir la noticia</a>
                </div>
            </article>
        </div>
    </section>
</template>

<script>
export default {
  name: 'SiteNoticias',
  props: {
    msg: String
  }
}
</script>

<style scoped>
.cajanot {
    width: 70%;
    height: 10%;
    background: #000000;
    color: #ffffff;
    border-radius: 1rem;

}

.noticias {

    display: flex;
    flex-wrap: wrap;
    border-radius: 1rem;
    padding: 1rem;
    padding-left: 5rem;

}

.noticias .notart {
    width: 40%;
    margin-top: 1rem;
    margin-left: 2rem;
    border: 2px solid rgb(255, 255, 255);
    height: 500px;
}

.cajanot h2 {
    color: rgb(238, 255, 0);
    text-align: center;
    padding: 1rem;
}

.notart h3 {
    width: 100%;
}

.notart p {

    width: 95%;
    height: 40%;
    padding: 0.3rem;
}

.notart img {
    width: 100%;
    
}

.divnot {
    width: 80%;
    height: 10%;
    padding-left: 1rem;

}

.divnot a {
    display: flex;
    margin: -10%;
    width: 40%;
    margin-left: 10rem;
    color:chartreuse;
    
    text-decoration: none;
}

.divnot a:hover {
    background-color: #ffffff;
}
</style>
