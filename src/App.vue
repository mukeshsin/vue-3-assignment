<template>
<!--Start Stop-->
<div :class="{
     buttonStop: gameStart,
      buttonStart: gameStop,
    }">
    <startMode class="playButton" @close="startGame" :delay="delay" :isPlaying="isPlaying" :gameStart="gameStart" :gameStop="gameStop" @open="stopGame">
    </startMode>
    <resultView class="resultReview" :score="score" :highScore="highScore" :isPlaying="isPlaying" :earlyTime="earlyTime"></resultView>
</div>
</template>

<script>
import startMode from "./components/Go.vue";
import resultView from "./components/Result.vue";
export default {
    name: "App",
    data() {
        return {
            gameStart: true,
            gameStop: false,
            delay: 5000,
            time: null,
            reactionTime: 0,
            score: 0,
            isPlaying: false,
            highScore: 0,
            class: null,
            earlyTime: false,
        };
    },
    components: {
        startMode,
        resultView,
    },

    methods: {
        startGame() {
            this.class = setTimeout(() => {
                this.startTimer();
                this.gameStart = true;
                this.gameStop = false;
                this.early = true;
            }, this.delay);
            this.isPlaying = !this.isPlaying;
            this.reactionTime = 0;
        },
        startTimer() {
            this.time = setInterval(() => {
                this.reactionTime += 10;
            }, 10);
        },
        stopGame() {
            clearTimeout(this.class);
            clearInterval(this.time);
            this.gameStart = false;
            this.gameStop = true;
            this.score = this.reactionTime / 1000;
            this.isPlaying = !this.isPlaying;
            if (this.highScore == 0) {
                this.highScore = this.score;
            }
            if (this.highScore > this.score && this.Score > 0) {
                this.highScore = this.score;
            }
            if (this.reactionTime == 0) {
                this.earlyTime = true;
            }
        },
    },
};
</script>

<style>
.buttonStart {
    width: 100%;
    height: 100vh;
    background-color: #42adf5;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.buttonStop {
    width: 100%;
    height: 100vh;
    background-color: green;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.playButton {
    margin-top: 10%;
}

.resultReview {
    margin-top: 20px;
}
</style>
