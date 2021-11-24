<template>
  <div class="field">
      <p>click here</p>
    <div
      class="control"
      :class="{ 'is-loading': loading,
       [`is-${size}`]: size,
        'has-icons-left':icon || type === 'password'
        }"
    >
      <input
        class="input"
        :type="inputType"
        placeholder="Primary input"
        :class="{
          [`is-${color}`]: color,
          [`is-${size}`]: size,
          'is-rounded': rounded,
          'is-loading': loading,
          
        }"
        v-bind="$attrs" 
        :value="modelValue"
        @input="(event) => $emit('update:modelValue', event.target.value)"
      />
      <!-- $attrs give all attribute in component base input -->

      <p class="icon is-left ml-4" v-if="type === 'password'">
        <i :class="passwordIcon"  @click="handleShowPassword"></i>
      </p>

      <p class="icon is-left ml-4" v-if="icon">
        <i :class="`fas fa-${icon}`"></i>
      </p>
    </div>


  </div>
</template>

<script>
export default {
  name: "BaseInput",
  inheritAttrs:false,
  props: {
    color: {
      type: String,
      required: false,
    },
    size: {
      type: String,
      required: false,
    },
    rounded: {
      type: Boolean,
      required: false,
    },
    loading: {
      type: Boolean,
      required: false,
    },
    icon: {
      type: String,
      required: false,
    },
    modelValue:{
        type:[String,Number],
        default:''
    },
    type:{
        type:String,
        default:'text'
    }
  },
  emits:['update:modelValue'],
  data(){
      return{
          inputType: this.type,
          showPassword: false
      }
  },
  computed:{
      passwordIcon(){
          return this.inputType === 'password' ? 'fas fa-eye' : 'fas fa-eye-slash'
      }
  },
  methods: {
      handleShowPassword(){
          if(!this.showPassword){
              this.inputType = 'text',
              this.showPassword = true
          }else{
              this.inputType = 'password',
              this.showPassword = false
          }
      }
  },
};
</script>

<style lang="scss">
@import "bulma/sass/utilities/_all.sass";
@import "bulma/sass/helpers/spacing.sass";
@import "bulma/sass/form/shared.sass";
@import "bulma/sass/form/tools.sass";

.control.has-icons-left .icon, .control.has-icons-right .icon {
    pointer-events: all !important;
}
@import "bulma/sass/form/input-textarea.sass";
</style>
