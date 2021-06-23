<template>
    <div>
        <h3 v-if="productList.length > 0" class="text-center">List of Added Products</h3>
        <hr>
        <div class="row product-container">
            <app-product v-bind:key="product" v-for="product in productList">
            <img class="card-img-top" :src="product.selectedImage" :alt="product.title">
            <div class="card-body">
            <h5 class="card-title">{{ product.title }}</h5>
            <small><strong>Count : </strong>{{ product.count }}</small><br>
            <small><strong>Price : </strong>{{ product.price }}</small><br>
            <small><strong>Total Amount : </strong>{{ product.totalPrice }}</small>
            </div>
        </app-product>
        </div>
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
                if(this.productList.length < 5){
                    this.productList.push(product);
                    eventBus.$emit("progressBarUpdated", this.productList.length);
                } else {
                    alert("You can't add more than 5 products!")
                }
            })
        }
    }
    
</script>
