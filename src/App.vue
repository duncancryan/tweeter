<template>
<div>
  <header>
  <h1>Twitter</h1>
  <h2>Total Likes: {{totalLikes}}</h2>
  </header>
  <ul>
    <user-tweet v-for="(tweet, index) in tweets" :key="index" :tweet="tweet">

    </user-tweet>
  </ul>
</div>
</template>

<script>
import UserTweet from './components/UserTweet.vue'

export default {
  name: 'app',
  data() {
  return {
    tweets:[
      {
        id: 1,
        name: 'James',
        handle: '@jokerjames',
        img: 'https://semantic-ui.com/images/avatar2/large/matthew.png',
        tweet: "If you don't succeed, dust yourself off and try again.",
        likes: 10,
      },
      {
        id: 2,
        name: 'Fatima',
        handle: '@fantasticfatima',
        img: 'https://semantic-ui.com/images/avatar2/large/molly.png',
        tweet: 'Better late than never but never late is better.',
        likes: 12,
      },
      {
        id: 3,
        name: 'Xin',
        handle: '@xeroxin',
        img: 'https://semantic-ui.com/images/avatar2/large/elyse.png',
        tweet: 'Beauty in the struggle, ugliness in the success.',
        likes: 18,
      }
    ]
  }
},
components: {
  'user-tweet': UserTweet
}, 
computed: {
        totalLikes: function() {
            return this.tweets.reduce((total, tweet) => total + tweet.likes, 0)
        }
    }
}
</script>

<style>
header {
  background: rgb(81, 138, 198);
  padding: 10px 20px;
  color: rgb(210, 216, 96);
  margin: 10px;
}

ul{
  list-style: none;
  display: flex;
  flex-direction: column;
}
div{
  width: 60%;
}

</style>