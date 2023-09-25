<template > 
    <div class="q-gutter-x-md q-mt-lg" >
          <q-btn push color="white" text-color="primary" label="Low-High" @click="asortByPrices()"/>
        
        <q-btn push color="white" text-color="primary" label="High-Low" @click="dsortByPrices()"/>
    </div>
    <div class="row justify-center q-gutter-xl q-mt-lg q-mb-md" style="background:#f1f3f6">
     <q-card class=" " v-for="product in products" :key="product.id"  style="height:auto; width:300px; ">
         <router-link :to="'/ProductList/'+product.id"  @click="showLoading">
        <div class="col-2">
        <!-- <h3 class="q-pt-md">{{ product.category}}</h3> -->
              <span class="col align-center">
                <span class="row"><img :src="product.image" class="q-ml-md q-mt-md" style="height:200px; width:100px"/>
                <h2 class="text-h4 text-bold q-ml-xl">{{" "+'$'+" "+product.price }}</h2></span>
                    <h3 class="text-h6 text-center">{{ product.title }}</h3> 
            </span> 
                <!-- <h2 style="font-family:Arial, Helvetica, sans-serif" class="text-h5">Description</h2> -->
               <!-- <h4 class="text-subtitle1 q-pb-lg">{{ product.description }}</h4> -->
               <!-- <q-btn class="q-mb-md" label="ADD TO CART" color="primary" @click="addToCart(product.title)"></q-btn> -->
            </div>
            </router-link>
            <router-view />
              </q-card>
              </div>
</template>

<script>
// import { createRouter, createWebHistory } from "vue-router";
import { useQuasar } from 'quasar'
import axios from 'axios'
import { onBeforeUnmount } from 'vue'
export default {
    setup() {
        const $q = useQuasar()
        let timer

        onBeforeUnmount(() => {
            if (timer !== void 0) {
                clearTimeout(timer)
                $q.loading.hide()
            }
        })

        return {
            showLoading() {
                $q.loading.show()

                // hiding in 2s
                timer = setTimeout(() => {
                    $q.loading.hide()
                    timer = void 0
                }, 2000)
            }
        }
    },
    data() {
        return {
           products:'',
        }
    },
    mounted()
    {
        this.productsApi();
    },
    methods: {
        
         productsApi() {
            const url = 'https://fakestoreapi.com/products';
            axios.get(url)
                .then((response) => {
                    this.products = response.data;
                })
        },
        asortByPrices()
        {
            this.products.sort((a, b) => a.price - b.price);
        },
         dsortByPrices() {
            this.products.sort((a, b) => b.price - a.price);
        },
    }

}
</script>

<style lang="scss" scoped>
.router-link {
  text-decoration: none;
}

</style>