<template>
  <div class="col-full">
    <h1>Not Found</h1>
    <p>
      Ooops, we couldn't find that your are looking for. Why don't you
      <router-link :to="{ name: 'Home'}">
        go home instead?
      </router-link>
    </p>
  </div>
</template>

<script>

export default {
  name: 'PageNotFound'
}
</script>

<style scoped>
  h1 {
    font-size: 6rem
  }
  p {
    font-size: 2rem;
    font-weight: 100;
  }
  div {
    text-align: center;
  }
</style>
