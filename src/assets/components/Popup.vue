<template>
    <div>
        <h2>this is popup</h2>
        <input type="text" v-model="names">
        <button @click="$emit('close' , names)">
            <slot></slot>        
        </button>
    </div>
</template>

<script>
export default {
name: 'PopUpComponent' , 
emits:  {
    close(names) {
        if(!names) {
            return false
        }else {
            return true
        }

    }
},
props: {
    name: String , 
} , 
data() {
    return {
        names: '' ,
    }
} , 


}
</script>

<style>
* {
     display: grid; 
     place-items: center;
}
</style>