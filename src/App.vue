<script>
import Header from './components/Header.vue'
import Jumbotron from './components/Jumbotron.vue'
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
    Jumbotron,
    PostCard
  }
}
</script>

<template>
  <div id="app">
    <Header />
    <Jumbotron />
    <main>
      <div class="container-fluid">
        <div class="container text-center">
          <h1>I MIEI POST</h1>
          <div class="row">
            <PostCard v-for="post in posts" :key="post.id" :post="post" />
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<style lang="scss">
@import './styles/general.scss';
@import './styles/partials/variables';

#app {
  margin-top: 80px;

  main {
    .container-fluid {
      background-color: $container-bg-color;

      .container {
        padding-top: 20px;

        h1 {
          color: white;
        }
      }
    }
  }
}
</style>
