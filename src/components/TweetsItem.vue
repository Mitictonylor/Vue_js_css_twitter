<template lang="html">
  <div class="tweet-item" v-bind:class="topRated">
      <p class="name"><img :src="tweet.img" alt="avatar" width="20"
         height="16">{{tweet.name}}</p>
      <p class="nickname">{{tweet.handle}}</p>
      <p class="tweet">"{{tweet.tweet}}"</p>
      <p class="likes"><img src="https://cdn0.iconfinder.com/data/icons/twitter-ui-flat/48/Twitter_UI-24-512.png" alt="like" width="20"
         height="15">{{tweet.likes}} </p>
         <button v-on:click="tweet.likes +=1">LIKE</button>


    </div>


</template>

<script>
export default {
  name: "TweetsItem",
  props: ["tweet"],
  computed: {
    topRated: function(){
      return this.tweet.likes >10 ? "top-rated" : "low-rated"
    },

  }

}
</script>

<style lang="css" scoped>
  .tweet-item{
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
  }
  .top-rated{
    background: lightblue;
    border-style: groove;
    border-color: blue
  }
  .low-rated{
    border-style:solid;
    border-color: lightgrey;
  }
.nickname{
  color: #697882;
  font-size: 12px;
  font-style: oblique;
  margin: 0;
  padding-left: 3%
}
.name{
  margin: 0;
  padding: 0;
  }
.button{
  background-color: #4CAF50; /* Green */
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
}
</style>
