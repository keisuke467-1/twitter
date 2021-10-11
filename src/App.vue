<template>
  <!-- 配列をv-forを使って分解し、子のTweetコンポーネントに渡していきます。 -->
  <div class="content">
    <Form v-on:tweet-event="tweetAction" />
    <div style="margin-top: 20px">
      <Tweet
        v-for="Tweet in AllTweet"
        v-bind:TweetObj="Tweet"
        v-bind:key="Tweet.tweet_id"
      />
    </div>
    <hr />
  </div>
</template>

<script>
import Form from "./components/Form.vue";
import Tweet from "./components/Tweet.vue";

export default {
  name: "App",
  components: {
    Form,
    Tweet,
  },
  data() {
    return {
      AllTweet: Array.of({
        tweet_id: 0,
        tweet_body: "初めてのツイート",
      }),
    };
  },
  methods: {
    // Formコンポーネントから受け取るTweetObjをこの配列にpush()メソッドによって追加していきます。
    tweetAction(TweetObj) {
      this.AllTweet.push(TweetObj);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
