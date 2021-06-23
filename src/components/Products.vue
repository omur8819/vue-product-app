<template>
    <div class="row product-container">
      <app-product v-bind:key="product" v-for="product in productList">
        <img class="card-img-top" src="/src/assets/default.png" alt="Card image cap">
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <small><strong>Count : </strong> 1</small><br>
          <small><strong>Price : </strong> 10</small><br>
          <small><strong>Total Amount : </strong> 10</small>
        </div>
      </app-product>
    </div>
</template>

<script>
    import Product from './Product.vue';
    import { eventBus } from '../main';
    export default {
        components: {
            appProduct: Product,
        },
        data: function(){
            return{
                productList: [],
            }
        },
        created(){
            eventBus.$on("productAdded", (product) => {
                this.productList.push(product);
            })
        }
    }
    
</script>
