<template>
  <div class="column">
    <ul><li>column:{{ info }}</li></ul>
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
    axios.get('http://192.168.100.134:8080/v1/column/pmlpml')
      .then(response => (this.info = JSON.parse(JSON.stringify(response.data))['AllColumns']))
      .catch(function (error) { 
        console.log(error);
      });
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
