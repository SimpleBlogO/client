<template>
  <div class="article">
    <ul>
    <li>ID: {{ id_ }}</li>
    <li>title : {{ title_}}</li>
    <li>author   : {{ author_}}</li>
    <li>content : {{ content_}}</li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      id_:null,
      title_:null,
      author_:null,
      content_:null
    }
  },
  mounted () {
    axios.get('http://192.168.100.134:8080/v1/article/Eayne')
      .then(response => (
        this.id_ = JSON.parse(JSON.stringify(response.data))['AllArticles'][0]['ID'],
        this.title_ = JSON.parse(JSON.stringify(response.data))['AllArticles'][0]['title'],
        this.author_ = JSON.parse(JSON.stringify(response.data))['AllArticles'][0]['author'],
        this.content_ = JSON.parse(JSON.stringify(response.data))['AllArticles'][0]['content']
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
