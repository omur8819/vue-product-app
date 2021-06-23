<template>
  <div class="container">
    <h1 class="text-center">Add Product Application</h1>
    <hr>
    <app-new-product></app-new-product>
    <br><br>
    <app-progress></app-progress>
    <br><br>
    <app-products></app-products>
  </div>


</template>

<script>
  import NewProduct from './components/NewProduct.vue';
  import Products from './components/Products.vue';
  import Progress from './components/Progress.vue';

  export default {
    components: {
      appNewProduct: NewProduct,
      appProducts: Products,
      appProgress: Progress,
    },
  }
</script>

<style scoped>
  body {
    background-color: aliceblue;
    padding-top: 20px;
    padding-bottom: 20px;
  }

  .card{
    margin-right: 5px;
    margin-bottom: 5px;
  }

  .card:last-child{
    margin-right: 0px;
  }

  .col-md-2{
    max-width: 15.666667%!important;
  }

  .product-container{
    margin-left: 15px;
  }

</style>


<!--
<template>
  <div>
    <img height="128" :src="product.selectedImage == null ? '/src/assets/default.png' : product.selectedImage">

    <input type="file" ref="file" @change="onChange($event)" value="Resim Seç">

    <button type="button" @click="$refs.file.click()">Resim Seç</button>

  </div>
</template>

<script>
  export default{
    data: function(){
      return{
        product: {
          title: null,
          selectedImage: null,
        }
      }
    },
    methods: {
      onChange(e){
        file = e.target.files[0];
        this.product.selectedImage = URL.createObjectURL(file)
      }
    },
  }

</script>
-->
