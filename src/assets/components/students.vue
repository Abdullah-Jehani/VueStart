<template>
    <div>
<h2 v-for="student in filterItems" :key="student.id">
<slot :id="student.id" :firstName="student.firstName" :lastNmae="student.lastName" :Age="student.Age" :city="student.city" :GPA="student.GPA"></slot>
</h2>

    </div>
</template>
<script>
export default {
    name: 'StudentsComponent' , 
    
    data() {
        return {
            students: [
                {
                    id: 1 , 
                    firstName: 'Ahmed' , 
                    lastName: 'Khalid' , 
                    Age: 23 , 
                    city: 'benghazi' , 
                    GPA: 3.2
                } , 
                {
                    id: 2, 
                    firstName: 'Omar' , 
                    lastName: 'Osama' , 
                    Age: 19 , 
                    city: 'benghazi' , 
                    GPA: 2.2
                } , 
                {
                    id: 3 , 
                    firstName: 'Abdullah' , 
                    lastName: 'Ahmed' , 
                    Age: 21 , 
                    city: 'benghazi' , 
                    GPA: 1.9
                }
            ] , 
        
        }
  
        
    } ,
    computed: {
        filterItems() {
            return this.students.filter(student => student.GPA === 1.9)
        }
    }
    
}
</script>