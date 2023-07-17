<template>
    <div>
    <h2>Title - {{title}} </h2>
<!-- we can apply attributes in specific tag - Yhis way if we apply style for component it will only apply for likes -->
    <h2 id="a" v-bind="$attrs"> Likes -  {{likes}} </h2> 
    <h2>  published - {{ isPublished ? 'This book Is Published' : 'This is Book has not Published  Yet ! '}}</h2>
</div>

</template>

<script>
export default {
    name: 'ArticleComponent' , 
    props: {
        title: {
            type : String , 
            required: true, 
            default : 'The Song of Fire And Blood' , 
        },
        likes: Number ,   
        isPublished : Boolean ,  
        
     } , 
     inheritAttrs: false , 
     // this will disable given the attriubutes by inherintence
    data() {
        return {
            name: {
                firstName: 'John' , 
                lastName: 'Doe' , 
            }

        }
    }

}
</script>