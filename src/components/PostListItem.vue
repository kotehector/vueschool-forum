<template>
  <div class="post">

    <div class="user-info">
      <a href="#" class="user-name">{{ user.name }}</a>
      <a href="#">
        <img 
          class="avatar-large"
          :src="user.avatar" alt="">
      </a>
      <p class="desktop-only text-small">
        {{ userPostsTotal }} posts.
      </p>
    </div>

    <div class="post-content">
      <div>
        {{ post.text }}
      </div>
    </div>

    <div class="post-date text-faded">
      <div>
        {{ post.publishedAt }}
      </div>
    </div>

  </div>
</template>

<script>
import sourceData from '@/data'

export default {
  name: 'PostListItem',

  props: {
    post: {
      required: true,
      type: Object
    }
  },

  data () {
    return {}
  },

  computed: {
    user () {
      return sourceData.users[this.post.userId]
    },

    userPostsTotal () {
      return Object.keys(this.user.posts).length
    }
  }
}
</script>

<style scoped>

</style>
