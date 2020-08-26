<template>
  <li :class="trendingClass">
      <aside>
        <img :src="tweet.img" alt="User Avatar">
      </aside>
      <section>
      <p><b>{{ tweet.name }}</b> {{tweet.handle}}</p>
      <p>{{tweet.tweet}}</p>
      <p>{{tweet.likes}} Likes</p>
      </section>
      <button v-on:click="tweet.likes += 1">Like</button>
  </li>
</template>

<script>
export default {
    name: "user-tweet",
    props: ['tweet'],
    computed: {
        trendingClass: function() {
            if (this.tweet.likes > 10) {
                return "trending"
            }
        }
    }
    }
</script>

<style scoped>
img{
    height: 100px;
    width: auto;
}
li{
    display: flex;
    padding: 10px;
    margin: 20px;
    background-color: blanchedalmond;
}
section{
    display: flex;
    flex-direction: column;
}
aside{
    margin: 10px;
}
.trending{
    display: flex;
    padding: 10px;
    margin: 20px;
    background-color: rgb(50, 130, 159);
    color: rgb(232, 214, 17);
}
button{
    height: fit-content;
    align-self: flex-end;
    margin: 10px;
}
</style>