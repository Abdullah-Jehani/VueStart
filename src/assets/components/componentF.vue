<template>
    <h2>ComponentF Name -  {{username}}</h2>
</template>
<script>
export default {
name: 'componentF',
inject: ['username'] 
}
</script>