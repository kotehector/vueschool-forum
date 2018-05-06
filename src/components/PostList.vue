<template>
  <div>
    <div class="thread-list">

      <h2 class="list-title">Posts</h2>

      <div class="post-list">
        <PostListItem
          v-for="post in posts"
          :post="post"
          :key="post['.key']"
        />
      </div>      

    </div>
  </div>
</template>

<script>
import PostListItem from './PostListItem'

export default {
  name: 'PostList',

  props: {
    posts: {
      required: true,
      type: Array
    }
  },

  data () {
    return {}
  },

  components: {
    PostListItem
  }

}
</script>

<style scoped>

</style>
