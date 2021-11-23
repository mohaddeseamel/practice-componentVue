<template>
    <button class="button" 
    :class="{[`is-${color}`] : color ,
     'is-light': isLight ,
      [`is-${size}`] :size ,
       'is-fullwidth':isFull,
       'is-outlined':outlined,
       'is-rounded': rounded,
       'is-loading': loading
       }"
       
    >
    <slot>default click</slot>
    </button>
</template>

<script>
export default {
    name:'BaseButton',
    props:{
        color:{
            type:String,
            required:false
        },
        isLight:{
            type:Boolean,
            default:false
        },
        size:{
            type:String,
            default:"normal"
        },
        isFull:{
            type:Boolean,
            default:false
        },
        outlined:{
            type:Boolean,
            default:false
        },
        rounded:{
            type:Boolean,
            default:false
        },
         loading:{
            type:Boolean,
            default:false
        }
    }
}
</script>

<style>
    
</style>