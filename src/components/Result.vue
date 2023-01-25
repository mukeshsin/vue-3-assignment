<template>
<div class="result">
    <template v-if="!isPlaying">
        <div class="score" v-if="earlyTime">
            <h2 v-if="score > 0">Your score is {{ score }}</h2>
        </div>
        <h3 class="score" v-else>click Go to test your reaction time!</h3>
    </template>
    <template v-else-if="isPlaying">
        <h2 class="score">Pay attention. Click stop when the color changes.</h2>
    </template>

    <h3 class="highscoretitle">Your High Score</h3>
    <h4 class="highscore">{{ highScore }} sec</h4>
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
    border-radius: 20px;
    border: none;
    background-color: lightskyblue;
}

.score {
    font-size: 18px;
    margin-left: 30px;
}

.highscoretitle {
    font-size: 20px;
    margin-left: 15px;
    margin-left: 30px;
}

.highscore {
    font-size: 20px;
    margin-left: 15px;
    margin-left: 30px;
}
</style>
