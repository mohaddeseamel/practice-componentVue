<template>
    <div class="app">
       <base-button>custom button</base-button>
       <base-button color="danger" is-light/>
       <base-button color="primary" size="medium" rounded />
       <base-button color="success" is-light outlined/>
       <base-button color="info" size="small" is-full @click="handleLoading" :loading="isLoading"/>
    </div>
    
</template>

<script>
import BaseButton from './components/BaseButton.vue'
export default {
    name:'App',
    data(){
        return{
            isLoading:false
        }
    },
   
   components:{
       BaseButton
   },
   methods: {
       handleLoading(){
           this.isLoading = true;
           console.log('loading')
       }
   },
}
</script>

<style lang="scss">
    @import "../node_modules/bulma/sass/utilities/_all";
    @import '../node_modules/bulma/sass/elements/button.sass';

</style>