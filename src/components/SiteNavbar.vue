<template>
    <nav>
        <ul>
            <li>
                <a href="#">M04PLAY</a>
            </li>
            <li>
                <a href="">VIDEOJUEGOS</a>
            </li>
            <li>
                <a href="#">NOTICIAS</a>
            </li>
            <li>
                <a href="#">RANKING</a>
            </li>
            <li>
                <a href="#">ENQUESTA</a>
            </li>
            <li>
                <a href="#">CONTACTO</a>
            </li>
        </ul>
    </nav>
</template>

<script>
export default {
  name: 'SiteNavbar',
  props: {
    msg: String
  }
}
</script>

<style scoped>
nav {
    position: sticky;
    top: 0;
    z-index: 1;
}

nav ul {
    background-color: #61f825;
    text-align: center;
    display: flex;
    justify-content: space-around;
    margin: 0rem;
    padding: 1rem;
    font-weight: bold;
}

nav ul li {
    list-style: none;
    padding: 0.1rem;
}

nav a {
    text-decoration: none;
    color: black
}
a:hover {
    color: blue;
}

</style>