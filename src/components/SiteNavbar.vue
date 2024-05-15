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

nav ul {
    background-color: #61f825;
    text-align: center;
    display: flex;
    justify-content: space-around;
    font-weight: bold;
    padding: 5px;
}

nav ul li {
    list-style: none;
    padding: 0.1rem;
}
li:hover{
    background-color: #0e4b00;;
}
nav a {
    text-decoration: none;
    color: black
}
a:hover {
    color: blue;
}
@media (max-width: 576px){
    nav ul{
        flex-direction: column;
        
    }
}
</style>