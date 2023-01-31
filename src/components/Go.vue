<template>
<button @click.prevent.capture="$emit('close')" class="start" v-show="!isPlaying"> Go </button>
<button @click.prevent.capture="$emit('open')" class="stop" v-show="isPlaying"> Stop </button>
</template>

<script>
export default {
    name: "startMode",
    data() {
        return {

        };
    },
    emit: ["close", "open"],
    props: ["delay", "isPlaying", "gameStart", "gameStop"],
};
</script>

<style>
.start {
    width: 500px;
    height: 150px;
    background-color: #68ae64;
    border: none;
    border-radius: 15px;
    align-items: center;
    font-size: 35px;
    color: white;
    margin-top: 60px;

}

.stop {
    width: 500px;
    height: 150px;
    background-color: #c86a67;
    border: none;
    border-radius: 20px;
    align-items: center;
    font-size: 35px;
    color: white;
    margin-top: 60px;

}
</style>
