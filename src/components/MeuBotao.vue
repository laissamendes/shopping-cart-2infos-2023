<script setup>
const props = defineProps({
    text: String
})
</script>

<template>
    <button>{{props.text}}</button>
</template>

<style scoped>
button{
background-color: rgb(0, 132, 255);
color: white;
border-style: solid;
border-color: white;
border-radius: 5px;

}
button:hover{
    background-color: rgb(0, 91, 177);

}
</style>