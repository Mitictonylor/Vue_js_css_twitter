<template lang="html">
  <div id="app">

    <Header v-bind:tweets="tweets"></Header>

    <form v-on:submit.prevent="saveTweet" >
      <select v-model="selected">
        <option v-for="tweet in tweets" v-bind:value="tweet"required>
          {{ tweet.handle }}
        </option>
      </select>

      <input type="text" name="tweet" placeholder="What's going on?" v-model="text" required>
      <input type="submit" class="btn" value="Submit">

    </form>

    <Tweets v-bind:tweets="tweets"></Tweets>

  </div>
</template>

<script>

import Header from './components/Header.vue'
import Tweets from './components/Tweets.vue'

export default {
  name: "App",
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
            ],
            selected:{},
            text: ""
          }
        },

components:{
            Header,
            Tweets
},

methods:{
          saveTweet: function(){
            const newObject ={
              id: this.tweets.length + 1,
              name: this.selected.name,
              img: this.selected.img,
              handle: this.selected.handle,
              tweet: this.text,
              likes: 0
            }

            this.tweets.push(newObject)
            console.log(this.tweets);
// console.log(this.tweets.length)
            // this.tweets=[...this.tweets,this.selected]
            this.selected = []
            this.text = ""
          },

        }

}
</script>

<style lang="css" scoped>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
.btn{
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}
.btn:hover{
  background: #666
}

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
