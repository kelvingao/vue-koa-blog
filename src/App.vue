<template>
  <div class="container">
    <app-header></app-header>
    <router-view></router-view>
    <app-footer></app-footer>
  </div>
</template>

<script>
import Footer from './components/footer.vue'
import Header from './components/header.vue'
import ShowBlogs from './components/showBlogs.vue'

export default {
  components: {
    'app-header': Header,
    'show-blogs': ShowBlogs,
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
