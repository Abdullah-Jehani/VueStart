<template>
    <h2>component C</h2>
    <componentE/>
</template>
<script>
import componentE from './componentE.vue'
export default {
name : 'componentC',
components: {
    componentE , 

}
}
</script>
