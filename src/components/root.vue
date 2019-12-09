<template>
  <div class="root">
    <ul>
    <li>article: {{ article_ }}</li>
    <li>column : {{ column_}}</li>
    <li>user   : {{ user_}}</li>
    <li>review : {{ review_}}</li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      article_:null,
      column_:null,
      user_:null,
      review_:null
    }
  },
  mounted () {
    axios.get('http://192.168.100.134:8080/v1')
      .then(response => (
        this.article_ = JSON.parse(JSON.stringify(response.data))['article'],
        this.column_ = JSON.parse(JSON.stringify(response.data))['column'],
        this.user_ = JSON.parse(JSON.stringify(response.data))['user'],
        this.review_ = JSON.parse(JSON.stringify(response.data))['review']
        ))
      .catch(function (error) { 
        console.log(error);
      });

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
