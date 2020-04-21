<template lang="html">
  <div>
    <div v-for="(tweet,index) in tweets" :key="index" >
      <TweetsItem v-bind:tweet="tweet"></TweetsItem>
    </div>

  </div>
</template>

<script>
import TweetsItem from './TweetsItem.vue'
export default {
  name: "Tweets",
  props:["tweets"],
  components: {
    TweetsItem
  }
}
</script>

<style lang="css" scoped>
</style>
