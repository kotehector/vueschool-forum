<template>
  <div>
    <div class="thread">
      <div>
        <p>
          <!-- <a :href="`/thread/${thread['.key']}`">{{ thread.title }}</a> -->
          <!-- <router-link :to="`/thread/${thread['.key']}`"> -->
          <router-link :to="{
            name: 'ThreadShow',
            params: {
              id: thread['.key']
            }  
          }">
            {{ thread.title }}
          </router-link>
        </p>
        <p class="text-faded text-xsmall">
          By <a href="profile.html">{{ user.name }}</a>, {{ thread.publishedAt }}.
        </p>
      </div>

      <div class="activity">
        <p class="replies-count">
          {{ totalReplies }} replies
        </p>

        <!-- <img class="avatar-medium" src="http://i0.kym-cdn.com/photos/images/facebook/000/010/934/46623-batman_pikachu_super.png" alt=""> -->

        <!-- <div>
          <p class="text-xsmall">
              <a href="profile.html">Bruce Wayne</a>
          </p>
          <p class="text-xsmall text-faded">2 hours ago</p>
        </div> -->
      </div>
    </div>
  </div>
</template>

<script>
import sourceData from '@/data'

export default {
  name: 'ThreadListItem',

  props: {
    thread: {
      required: true,
      type: Object
    }
  },

  data () {
    return {}
  },

  computed: {
    totalReplies () {
      return Object.keys(this.thread.posts).length - 1
    },

    user () {
      return sourceData.users[this.thread.userId]
    }
  }
}
</script>

<style scoped>

</style>
