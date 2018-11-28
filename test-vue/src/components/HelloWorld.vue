<template>
  <div class="hello">
    <h1>{{ items.id }}</h1>
    <h2>{{ items.date_gmt}}</h2>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'HelloWorld',
  data () {
    return {
      items: null
    }
  },
  created () {
    axios.get('http://localhost:8888/wp-json/wp/v2/posts/58').then(res => {
      this.items = res.data
    })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
