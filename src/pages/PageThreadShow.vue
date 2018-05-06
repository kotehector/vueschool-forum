<template lang="">
  <div class="col-large push-top"> 
    <h1>{{ thread.title }}</h1>
    <PostList :posts='posts'/>
  </div>
</template>

<script>
import sourceData from '@/data'
import PostList from '@/components/PostList'

export default {
  name: 'PageThreadShow',

  props: {
    id: {
      required: true,
      type: String
    }
  },

  data () {
    return {
      thread: sourceData.threads[this.id]
    }
  },

  components: {
    PostList
  },

  computed: {
    posts () {
      const postIds = Object.values(this.thread.posts)
      console.log('POSTSIDS ', postIds)
      return Object.values(sourceData.posts)
        .filter(post => postIds.includes(post['.key']))
    }
  }
}
</script>
