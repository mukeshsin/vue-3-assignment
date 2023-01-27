<template>
<div class="result">
    <template v-if="!isPlaying">
        <div class="score" v-if="earlyTime">

            <h2 v-if="score > 0">Your Score is: {{ score }}</h2>
            <h2 v-else class="score">Too yearly</h2>
        </div>
        <h3 class="score" v-else>click Go to test your reaction time!</h3>
    </template>
    <template v-else-if="isPlaying">
        <h2 class="score">Pay attention.Click stop when the color changes.</h2>
    </template>
    <div class="highScore">
        <h3>Your High Score is:</h3>
        <h4>{{ score }} sec</h4>
    </div>
</div>
</template>

<script>
export default {
    name: "resultView",

    data() {
        return {};
    },

    props: ["score", "highScore", "isPlaying", "earlyTime"],
};
</script>

<style>
.result {
    width: 500px;
    height: 150px;
    border-radius: 15px;
    border: none;
    background-color: lightskyblue;
    padding: 3px 5px 3px 5px;
}

.score {
    font-size: 17px;
    margin-top:15px;
    margin-left:10px;
}
.highScore{
    font-size: 15px;
    margin-top:15px;
    margin-left:10px;
}
</style>
