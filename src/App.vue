<template>
  <div v-for="product in products">
    <template v-if=" product.name  != 'Papa'">
      <Card  :product = "product" :addProduct="addProduct" @viewProductDetail="viewProductDetail"/>
    </template>
    <template v-else>
      <CardComp :product = "product" :addProduct="addProduct" @viewProductDetail="viewProductDetail" />
    </template>
  </div>
</template>

<script>
import Card from './components/Card.vue'
import CardComp from './components/CardComp.vue'

export default {

  components: {
    Card,
    CardComp
  }, 
  setup(){

    const addProduct = () => {
        alert("Producto Agregado")
    }

    const viewProductDetail = (product) => {
        alert(JSON.stringify(product))
    }

    const products = [
        {
          name: "Pitaya",
          unid: "Libra",
          price: 4000,
          image: "https://exoticfruitbox.com/wp-content/uploads/2017/08/Depositphotos_2252971_original-300x239.jpg",
        },
        {
          name: "Granada",
          unid: "Libra",
          price: 3000,
          image: "https://exoticfruitbox.com/wp-content/uploads/2015/10/granada-100x100.jpg",
        },
        {
          name: "Papa",
          unid: "Libra",
          price: 5000,
          image: "https://politika.com.co/wp-content/uploads/2022/04/depositphotos_7899312-stock-photo-raw-potatoes.webp",
        },
        {
          name: "Aguacate",
          unid: "Libra",
          price: 6500,
          image: "https://exoticfruitbox.com/wp-content/uploads/2015/10/aguacate-100x100.jpg",
        }
    ];

    return{
      products,
      addProduct,
      viewProductDetail
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
