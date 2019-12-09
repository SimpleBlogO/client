<template>
  <div class="article">
    {{ info }}
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      info:null
    }
  },
  mounted () {
    axios.get('http://192.168.100.134:8080/v1/article/Eayne')
      .then(response => (this.info = response.data))
      .catch(function (error) { 
        console.log(error);
      });
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
