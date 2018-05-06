<template>
  <div>
    <div class="thread-list">

      <h2 class="list-title">Threads</h2>

      <ThreadListItem
        v-for="thread in threads"
        :thread="thread"
        :key="thread['.key']"/>

    </div>
    
    <!-- <div 
      class="col-large push-top"
      v-for="thread in threads"
      :key="thread.key">

      <h2>TITLE THREAD: {{ thread.title }}</h2>
      
      <div class="post-list">
        <div 
          class="post"
          v-for="postId in thread.posts"
          :key="postId">
          
          <div class="user-info">
            <a href="#" class="user-name">{{ users[posts[postId].userId].name }}</a>
            <a href="#">
              <img 
                class="avatar-large"
                :src="users[posts[postId].userId].avatar" alt="">
            </a>
            <p class="desktop-only text-small">
              107 posts.
            </p>
          </div>

          <div class="post-content">
            <div>
              {{ posts[postId].text }}
            </div>
          </div>

          <div class="post-date text-faded">
            <div>
              {{ posts[postId].publishedAt }}
            </div>
          </div>

        </div>
      </div>
      
    </div> -->
  </div>
</template>

<script>
import ThreadListItem from './ThreadListItem'

export default {
  name: 'ThreadList',

  props: {
    threads: {
      required: true,
      type: Array
    }
  },

  data () {
    return {}
  },

  components: {
    ThreadListItem
  }

}
</script>

<style scoped>

</style>
