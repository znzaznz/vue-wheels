<template>
  <svg class="icon">
    <use :xlink:href="`#i-${name}`"></use>
  </svg>
</template>

<script>
export default {
  name: "SvgIcon",
  props:["name"]
}
</script>

<style scoped>

</style>