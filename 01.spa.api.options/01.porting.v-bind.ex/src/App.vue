<template>
  <!-- when embeding components here are possible syntax alternatives:  -->
  <!-- lower case with hypens explicit closing tag: RECOMMENED for both SPA nad in-broser modes  -->
  <progress-bar class="wrapper" style="width: 50%"></progress-bar>
  <!-- lower case with hypens self closed tag - can be used in SPA but might not work in-browser -->
  <progress-bar class="wrapper" style="width: 100%" />
  <!-- pascal case with self closed tag - shortcut for SPA only -->
  <ProgressBar class="wrapper" style="width: 75%" />
  <!-- pascal case with explict closing tag - SPA only -->
  <ProgressBar class="wrapper" style="width: 25%"></ProgressBar>
  <!-- Plase notice style definition on components: because this componet has single root element (div) styles will be applied to inner component element. -->
</template>

<script>
// component is declared in separate file and imported here
import ProgressBar from './components/ProgressBar.vue'

export default {
  // for options api imported components have to be explicity declared inside options so that can exposed and used inside the template.
  components: {
    ProgressBar,
  },
}
</script>

<style scoped>
.wrapper {
  padding: 1rem;
}
</style>
