<template>
  <div class="login">
    <Nav />
  </div>
</template>

<script>
import Nav from './Nav.vue'
export default {
    name: "Login",
    components: {
      Nav
        
    }
}
</script>

<style lang="scss" scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

</style>