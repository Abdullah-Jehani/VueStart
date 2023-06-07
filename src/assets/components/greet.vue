<template>
    <h2> hello {{name}} Also Known As : {{heroName}}</h2>
</template>

<script>
export default {
    name: 'greetPrint' , 
    props : ['name' , 'heroName'] , 
    data() {
        return {
            greet : 'Abdullah'
        }
    }

}
</script>