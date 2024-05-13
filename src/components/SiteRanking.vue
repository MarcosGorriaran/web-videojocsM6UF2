<template>
    <section class="rank">
        <h2>RANKING</h2>
        <article class="rankart">
            <div class="divimg">
                <img src="@/assets/cara1.jpg" class="imgredonda" alt="jugador">
            </div>
            <h3>Nombre</h3>
            <p>Puntuacion</p>
        </article>
        <article class="rankart">
            <div class="divimg">
                <img src="@/assets/cara2.jpg" class="imgredonda" alt="jugador">
            </div>
            <h3>Nombre</h3>
            <p>Puntuacion</p>
        </article>
        <article class="rankart">
            <div class="divimg">
                <img src="@/assets/cara3.jpg" class="imgredonda" alt="jugador">
            </div>
            <h3>Nombre</h3>
            <p>Puntuacion</p>
        </article>
        <article class="rankart">
            <div class="divimg">
                <img src="@/assets/cara4.jpg" class="imgredonda" alt="jugador">
            </div>
            <h3>Nombre</h3>
            <p>Puntuacion</p>
        </article>
        <article class="rankart">
            <div class="divimg">
                <img src="@/assets/cara1.jpg" class="imgredonda" alt="jugador">
            </div>
            <h3>Nombre</h3>
            <p>Puntuacion</p>
        </article>
        <article class="rankart">
            <div class="divimg">
                <img src="@/assets/cara2.jpg" class="imgredonda" alt="jugador">
            </div>
            <h3>Nombre</h3>
            <p>Puntuacion</p>
        </article>
    </section>
</template>

<script>
export default {
  name: 'SiteRanking',
  props: {
    msg: String
  }
}
</script>

<style scoped>
.rank {
    display: flex;
    flex-wrap: wrap;
    width: 100%;
    justify-content: space-around;
    background: #5a4292
}

.rank h2 {
    text-align: center;
    width: 100%;
    color: rgb(238, 255, 0);
    padding: 1rem;

}

.rankart {
    width: 15%;
    height: 50%;
    padding: 0.5rem;
    align-content: center;
}

.rankart h3 {
    text-align: center;
}

.rankart {

    text-align: center;
}

.imgredonda {
    align-content: center;
    width: 150px;
    height: 150px;
    border-radius: 150px;
}

.divimg {
    width: 100%;
    align-content: center;
}
</style>