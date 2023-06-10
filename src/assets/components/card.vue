<template>
    <div class="card">
       <slot>Default Content</slot>
    </div>
</template> 
<script>
export default {
name: 'CardComponent' ,


}
</script>

<style>
.card {
    box-shadow: 0 4px 8px 0 rgba(0 , 0 , 0 , 0.2); 
    transition: .3s; 
    padding: 16px; 
    margin-bottom: 20px; 
    width: 200px;
    margin-top: 20px ;
} 
.card:hover {
    box-shadow: 0 8px 16px 0   rgba(0 , 0 , 0 , 0.2);  ;
}
</style>