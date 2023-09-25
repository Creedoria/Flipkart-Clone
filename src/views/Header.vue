<template>
    <link
      rel="stylesheet"
      href="https://fonts.googleapis.com/icon?family=Material+Icons"
    >
    <!-- <div  style="height:100px; width:100%; background:black; " class="row inline justify-around">
        <img style="height:100px;" :src="url"/>
        <q-input filled v-model="text" label="Search for products here" class="q-mt-lg" style="background:white;height:50px; width:500px;"/>
         <options class="q-mt-md" />
         <q-btn  class="q-mt-lg" color="primary" glossy icon="local_grocery_store" style="height:50px"/>
     </div> -->

     
        <q-layout view="lH lpr lFf" container style="height: 70px" class="shadow-2 rounded-borders" >
          <q-header elevated class="bg-white">
            <q-toolbar class=" ">
               <div >
                  <img :src="url" style="height:80px; width:150px;" dense >
                 </div>
             <q-input outlined v-model="text" label="Search for Products,Brands and More" class="
 shadow-2 rounded-borders q-mt-xs q-mb-md q-ml-xl "
             style="width:50%;background:#f1f3f6 "  />
              <!-- <q-btn flat round dense icon="whatshot" /> -->
            </q-toolbar>
          </q-header>
          </q-layout>
</template>

<script>
// import logo from '../assets/logo.jpg'
// import logo1 from '../assets/cart.png'
import logo from '../assets/flipkart_logo.png'
export default {
    data() {
        return {
            // url: logo,
            // url1:logo1,
          text: '',
            url:logo,
        }
    },
    methods: {
    }
}
</script>

<style lang="scss" scoped>

</style>