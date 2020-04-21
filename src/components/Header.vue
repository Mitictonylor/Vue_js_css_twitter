<template lang="html">
  <header class="header">
    <h1><img src="https://i0.wp.com/techweez.com/wp-content/uploads/2014/03/twt.jpeg?fit=610%2C320&ssl=1" alt="logo" width="200"
       height="80">TWITTER</h1>
       <p>Total tweets: {{totalLikes}}</p>
  </header>
</template>

<script>
export default {
  name: "Header",
  props: ["tweets"],
  computed: {
    totalLikes: function(){
      return this.tweets.reduce((total, tweet)=> total + tweet.likes, 0 );
    }
}
  }
</script>

<style lang="css" scoped>
.header{
  background: lightblue;
  color: white;
  text-align: center;
  padding: 5px
}
h1 img
{float:left;margin:0 5px 0 0}
.header p{
  color: black;
  padding-right: 10px;
}

</style>
