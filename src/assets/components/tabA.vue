<template>
    <div>
        <ul>
            <li>IT foundation</li>
            <li>Programming 1</li>
            <li>MATH 1</li>
            <li>English 1</li>
            <li>Arabic</li>
        </ul>
        <input type="text" v-model="name">
    </div>
</template> 
<script>
export default {
    name: 'tabA' , 
    data() {
        return {
            name: '' , 

        }
    }
}
</script>