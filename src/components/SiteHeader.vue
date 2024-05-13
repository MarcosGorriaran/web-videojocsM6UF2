<template>
    <header>
        <figure>
            <img src="@/assets/logo.png" alt="logo">
        </figure>
    </header>
</template>
<script>
export default {
  name: 'SiteHeader',
  props: {
    msg: String
  }
}
</script>

<style scoped>
header {
    width: 100%;
    padding: 0px;
    background-color: #000000;
    text-align: center;
}
img{
  width: 100%;
  height: 250px;
}
</style>
