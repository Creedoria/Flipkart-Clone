<template>
     <link
          rel="stylesheet"
          href="https://fonts.googleapis.com/icon?family=Material+Icons"
        >
   <div class="row justify-center q-mt-xl ">
    <q-card class="bg-blue-14 box-shadow" style="height:600px; width:400px;">
    <h4 class="text-white q-ml-lg ">Login</h4>
     <h6 class="text-white q-ml-lg q-mr-lg text-center">Get access to your Orders, Wishlist and Recommendations</h6>
     <img :src="url" >
    </q-card>
    <q-card class=" row items-center shadow" style="height:600px; width:500px;">
        <div>
           <q-input filled v-model="email" type="email" suffix="@gmail.com" style="width:400px" class="q-ml-xl">
        <template v-slot:before>
          <q-icon name="mail" />
        </template>
      </q-input>
      <q-input filled type="password" class="q-ml-xl q-mt-md bg-grey-2" v-model="password" label="password" style="width:400px">
        <template v-slot:before>
              <q-icon name="password" />
            </template></q-input>
           <q-btn class="bg-orange-14 text-white q-mt-lg q-ml-xl" label="Login" style="width:400px" ><router-link :to="'/ProductsList'">Login</router-link></q-btn>
      </div>
    </q-card>
   <!-- <router-view /> -->
   </div>
</template>

<script>
import login from '../assets/login.jpg'
export default {
    setup() {

        return {}
    },
    data() {
        return {
            url: login,
            email: '',
            password: ''
        }
    },
    methods: {
    }
}
</script>

<style lang="scss" scoped>

</style>