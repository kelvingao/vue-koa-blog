<template>
    <footer>
        <p> Copyright &copy; {{ copyright }} </p>
    </footer>     

</template>

<script>
export default {
  data () {
    return {
        copyright: '2017 Kelvin Gao'
    }
  }
}
</script>
    
 
<style scoped>
footer {
    background: #222;
    padding: 6px;
}
p {
    color: lightgreen;
    text-align: center;
}

</style>
