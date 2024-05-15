<template>
    <footer>
        <div class="SocialNetworks">
            <div class="fooimg">
                <img src="@/assets/instagram.png" alt="Instagram">
                <img src="@/assets/facebook.png" alt="Facebook">
            </div>
            <div class="divad">
                <address>Carrer d'Aguablava 121</address>
                <address>08033 Barcelona</address>
            </div>
        </div>
    </footer>
</template>

<script>
export default {
  name: 'SiteFooter',
  props: {
    msg: String
  }
}
</script>


<style scoped>
footer {
    width: 90%;
    text-align: center;
    background: #ffffff;

}

div.SocialNetworks {
    display: flex;
    
    width: 65%;

}

.fooimg img {
    width: 5%;
    float: left;
    padding: 0.5rem;
    background: #ffffff;
}

.divad {

    justify-content: space-around;
    width: 100%;
    align-content: center;
    background: #ffffff;

}

address {
    width: 70%;
}
</style>