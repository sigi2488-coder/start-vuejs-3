<template>
    <div class="card">

   <div class="card-header">
    <h2 class="card-title">{{ product.name }}</h2>
  </div>
  <div class="card-body">
    <img  v-bind:src="product.image" width="250" height="220"/>
    <p>Unidad: {{ product.unid }}</p>
        <span>Precio: ${{ product.price }}</span>
  </div>
  <div class="card-footer">
    <button @click="addItem">Comprar</button>
    <button @click="viewDetail(product)">Ver mas</button>
  </div>
</div>
</template>
<script>
    export default{
        components(){},
        data (){
            return {
                image: "https://www.quironsalud.com/blogs/es/hablemos-nutricion/tomate.ficheros/2299323-tomate1.jpg?width=201&height=156&aspectRatio=true"
            }
        },
        computed(){},
        watch(){},
        methods: {
            addItem(){
                alert("Comprado")
            },
            viewDetail(product){
              this.$emit('viewProductDetail', product);
            }
        },
        mounted() {
            
        },
        props: {
          product: {
            type: Object,
            required: true
          },
          addProduct: Function,
        },
        emits: ["viewProductDetail"]
    }
</script>
<style>

.card {
  /* Tamaño y márgenes */
  width: 300px;
  margin: 20px auto;
  padding: 20px;

  /* Color de fondo y borde */
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 5px;

  /* Sombra */
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.card-header {
  /* Color de fondo del encabezado */
  background-color: #f0f0f0;
  padding: 10px;
}

.card-title {
  /* Estilo del título */
  font-size: 18px;
  font-weight: bold;
}

.card-body {
    width: 300px;
}

.card-footer {
  /* Pie de la tarjeta */
  text-align: right;
}
</style>