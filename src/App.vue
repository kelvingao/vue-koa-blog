<template>
  <div>
    <app-header></app-header>
    <app-footer></app-footer>
  </div>
</template>

<script>
import Footer from './components/footer.vue'
import Header from './components/header.vue'

export default {
  components: {
    'app-header': Header,
    'app-footer': Footer
  },
  data () {
    return {
    
    }
  }
}
</script>

<style>

</style>
