<script>
import Header from './components/Header.vue'
import PostCard from './components/PostCard.vue'
import axios from 'axios';

const API = "http://localhost:3000/posts"

export default {
  name: 'App',
  data() {
    return {
      posts: []
    }
  },
  mounted() {
    axios.get(API)
      .then(res => {

        this.posts = res.data;

        console.log(JSON.stringify(this.posts, null, 2));
      })
      .catch(err => console.error(err));
  },
  components: {
    Header,
    PostCard
  }
}
</script>

<template>
  <body>
    <Header />
    <main>
      <h1>I MIEI POST</h1>

      <div class="container">
        <div class="row">
          <PostCard v-for="post in posts" :key="post.id" :post="post" />
        </div>
      </div>
    </main>
  </body>
</template>

<style lang="scss">
@use './styles/general.scss';
</style>
