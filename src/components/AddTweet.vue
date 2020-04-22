<template lang="html">

  <div class="">
    <form v-on:submit.prevent="saveTweet" >
      <select v-model="selected">
        <option v-for="(tweet,index) in tweets" :key="index"v-bind:value="tweet"required>
          {{ tweet.handle }}
        </option>

      </select>
      <input type="text" name="tweet" placeholder="What's going on?" v-model="text" required>
      <input type="submit" class="btn" value="Submit">

    </form>
  </div>

</template>

<script>

export default {
  name: "AddTweet",

  props: ["tweets"],

  data(){
    return{
      selected: [],
      text: ""
    }
  },

  methods:{
    saveTweet: function(){

      const newTweet = this.selected
      newTweet.tweet = this.text
      newTweet.likes = 0
      console.log(newTweet)
      this.$emit("add-tweet", newTweet);
      this.selected = []
      this.text = ""
    }
  }
}
</script>

<style lang="css" scoped>

  form{
    display: flex
  }
  input[type="text"]{
    flex: 40;
    padding: 5px
  }
  input[type='submit']{
    flex: 8
  }
  select{
    flex:10
  }
</style>
