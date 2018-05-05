<template>
  <div class="hello">
    <h1>Welcome to the Forum!</h1>
    <div 
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
      
    </div>
  </div>
</template>

<script>
import sourceData from '@/data'
console.log('categories: ', Object.keys(sourceData.categories))
console.log('forums: ', Object.keys(sourceData.forums))
console.log('moderators: ', Object.keys(sourceData.moderators))
console.log('posts: ', Object.keys(sourceData.posts))
console.log('stats: ', Object.keys(sourceData.stats))
console.log('threads: ', Object.keys(sourceData.threads))
console.log('users: ', Object.keys(sourceData.users))

export default {
  name: 'HelloWorld',
  data () {
    return {
      categories: sourceData.categories,
      forums: sourceData.forums,
      moderators: sourceData.moderators,
      posts: sourceData.posts,
      stats: sourceData.stats,
      threads: sourceData.threads,
      users: sourceData.users
    }
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
