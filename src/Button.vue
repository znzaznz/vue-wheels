<template>
  <button class="g-button" :class="{[`icon-${iconPosition}`]:true}">
    <svg class="icon" v-if="icons">
      <use :xlink:href="`#i-${icons}`"></use>
    </svg>
    <slot></slot>
  </button>
</template>
<script>
export default {
  name: "Button",
  // props:["icons","iconPosition"],
  props:{
    icons: {},
    iconPosition:{
      type:String,
      default:"left",
      validator(value){
        return !(value !== "left" && value !== "right")
      }
    }
  }
}
</script>

<style lang="scss">
.g-button {
  display: inline-flex;
  justify-content: center;
  align-items: center;
  font-size: var(--font-size);
  height: var(--button-height);
  vertical-align: middle;
  padding: 0 1em;
  border-radius: var(--button-radius);
  border: 1px solid var(--border-color);
  background: var(--button-bg);
  .icon{
    width: 1em;
    height: 1em;
    display: none;
  }
  &:hover {
    border-color: var(--border-color-hover);
  }

  &:active {
    background-color: var(--button-active-background);
  }

  &:focus {
    outline: none;
  }
  &.icon-right{
    >.icon{
      display: block;
      order: 2;
      margin-left: 0.2em;
    }
  }
  &.icon-left{
    >.icon{
      display: block;
      margin-right: 0.2em;
    }
  }
}
</style>