<template>
    <div>
        <h2 v-for="sale in sales" :key="sale.id">
        <slot :id="sale.id" :ProductName="sale.ProductName" :date="sale.date" :price="sale.price" ></slot>
        </h2>
    </div>
</template>
<script>
export default {
    name : 'SalesComponent' ,
    data() {
         return { 
            sales: [
                {
                    id: 1 , 
                    ProductName: 'PS5' , 
                    date: '1/1/2023' , 
                    price: 1000
                } , 
                {
                    id: 2 , 
                    ProductName: 'IPHONE 14' , 
                    date: '1/1/2023' , 
                    price: 2000                } , 
                {
                    id: 3 , 
                    ProductName: 'SAMSUNG S23' , 
                    date: '1/1/2023' , 
                    price: 3000
                }
            ]
         }
    }
}
</script>