<template>
  <li>
      <aside>
        <img :src="tweet.img" alt="User Avatar">
      </aside>
      <p><b>{{ tweet.name }}</b> {{tweet.handle}}</p>
      <p>{{tweet.tweet}}</p>
      <p>{{tweet.likes}}</p>
  </li>
</template>

<script>
export default {
    name: "user-tweet",
    props: ['tweet']

}
</script>

<style scoped>
img{
    height: 30px;
    width: auto;
}
</style>