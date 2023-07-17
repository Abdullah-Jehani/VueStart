<template>
    <div>
        <h2 v-for="teatcher in teatchers" :key="teatcher.id">
        <slot :id="teatcher.id" :firstName="teatcher.firstName" :lastName="teatcher.lastName" :location="teatcher.location" :degree="teatcher.degree" :salary="teatcher.salary" :yearsofEXP="teatcher.yearsofEXP"></slot>
        </h2>
    </div>
</template>

<script>
export default {
    name: 'teatchersComponent' , 
    data() {
        return {
            teatchers: [
                {
                    id: 1  ,
                    firstName: 'Abdullah' , 
                    lastName: 'Aljehani' , 
                    location: 'Benghazi' ,
                    degree: 'MSC' , 
                    salary: 10000 , 
                    yearsofEXP: 2 

                } ,
                {
                    id: 2 , 
                    firstName: 'Osama' , 
                    lastName: 'Khalid' , 
                    location: 'Tripoli' ,
                    degree: 'BCS' , 
                    salary: 9000 , 
                    yearsofEXP: 1 

                } ,
                {
                    id: 3 , 
                    firstName: 'Ali' , 
                    lastName: 'Omran' , 
                    location: 'Misurata' ,
                    degree: 'MSC' , 
                    salary: 10000 , 
                    yearsofEXP: 3 

                } 
            ]
        }
    }
}
</script>
