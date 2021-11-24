<template>
    <div class="app">
       <!-- <base-button>custom button</base-button>
       <base-button color="danger" is-light/>
       <base-button color="primary" size="medium" rounded />
       <base-button color="success" is-light outlined/>
       <base-button color="info" size="small" is-full @click="handleLoading" :loading="isLoading"/> -->
       <!-- <base-input color="primary" size="medium"/>
       <base-input color="danger" size="small" /> -->
        <!-- <base-input loading size="large" icon="envelope" type="password" /> -->
       <base-input  v-model="name"/>
       <base-input type="email" v-model="email" />
       <base-input type="password" v-model="password" />
    </div>
    
</template>

<script>
// import BaseButton from './components/BaseButton.vue'
import BaseInput from './components/BaseInput'
export default {
    name:'App',
    data(){
        return{
            isLoading:false,
            name:'mohaddese',
            email:'moha@gmail.com',
            password:''
        }
    },
   
   components:{
    //    BaseButton,
       BaseInput
   },
   methods: {
       handleLoading(){
           this.isLoading = true;
           console.log('loading')
       },
       handleClick(){
           console.log('click on component')
       }
   },
}
</script>

<style lang="scss">
    @import "../node_modules/bulma/sass/utilities/_all";
    @import '../node_modules/bulma/sass/elements/button.sass';

</style>