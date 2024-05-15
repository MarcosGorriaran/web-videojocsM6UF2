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
    background-color: #000000;
    text-align: center;
}
header img{
  width: 100%;
}
</style>
