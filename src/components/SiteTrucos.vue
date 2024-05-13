<template>
    <section class="truco">
            <h2>TRUCOS</h2>
            <article class="tr1">
                <h4>Grand Theft Auto</h4>
                <p>Para aparecer barcos: 362-555-050</p>
                <p>Para aparecer salud: 482-555-050</p>
            </article>
            <article class="tr1">
                <h4>League of Legends</h4>
                <p>Hechizos de invocador: te explicamos qué son y cómo funciona cada uno.</p>
                <p>Subir de nivel rápido: descubre todas las formas de ganar puntos de experiencia (EXP).</p>
                <p>Recompensas de cuenta: aquí mostramos todos los premios que ganarás por subir tu nivel en LoL.</p>
            </article>
        </section>
</template>
<script>
export default {
  name: 'SiteTrucos',
  props: {
    msg: String
  }
}
</script>

<style scoped>
.truco {
    flex-direction: column;
    width: 25%;
    height: 80rem;
    margin-left: 0.5rem;
    background: #61f825;

}

.truco h2 {
    text-align: center;
    color: #000000;

}

.tr1 {
    width: 88%;
    padding: 1rem;
    height: 10rem;
    padding: 1rem;
    color: #000000;

}

.tr1 h4 {
    font-weight: bold;
}
</style>