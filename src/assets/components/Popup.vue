<template>
    <div>
        <h2>this is popup yes its man</h2>
        <button @click="$emit('close')">{{name}}</button>
    </div>
</template>

<script>
export default {
name: 'PopUpComponent' , 
emits: ['close'],
props: {
    name: String , 
}
}
</script>

<style>
* {
     display: grid; 
     place-items: center;
}
</style>