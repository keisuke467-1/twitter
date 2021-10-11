<template>
    <div class="form-group">
        <textarea 
        name="form" 
        id="" class="" 
        cols="60" 
        rows="5" 
        placeholder="いまなにしてる" 
        v-model="TweetObj.tweet_body">
        </textarea>
        <!--v-model… data変数とフォームの値を連動させることが出来る -->
        <br>
        <button class="btn btn-primary" v-on:click="doTweet">ツイート</button>
        <!-- v-on ディレクティブを使うことで、DOM イベントの購読、イベント発火時の JavaScript の実行が可能になる -->
        <!-- 「ツイートする」ボタンを押すと、clickイベントにより$emitを動作させて、親コンポーネントのAppにツイートのデータを渡します。 -->
    </div>
</template>

<script>
export default {
    name: 'Form',
    data() {
        return {
            // TweetObjは最終的にバックエンド側でデータベースに接続することを念頭に主キーとなるtweet_idと ツイートの本文であるtweet_bodyを持たせました。
            TweetObj:{
                tweet_id:0,
                tweet_body:''
            },
        }
    },
    methods: {
        doAction() {
            this.TweetObj.tweet_id += 1
            this.$emit('tweet-event',this.TweetObj)
        }
    }
}
</script>