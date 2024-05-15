<template>
        <img :src="file" alt="">
        <input type="file" @change="ReadFile">
    
</template>
<script>
export default {
    name: 'InputFile',
    props:{
        file:Object
    },
    methods:{
        getBase64(file) {
        return new Promise((resolve,reject)=>{
        var reader = new FileReader();
        reader.readAsDataURL(file);
        reader.onload = function () {
        resolve(reader.result)
        };
        reader.onerror = reject
        })
    },
    async ReadFile(event){
        console.log(this.file);
        let data = await this.getBase64(event.target.files[0])
        this.$emit("fileChange",data);
    },
    
  }
}
</script>
<style scoped>
img{
    width: 30%;
}
</style>