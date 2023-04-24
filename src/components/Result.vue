<template>
    <div class="result">
        <h2>Reaction Time: {{ score }}ms</h2>
        <p>{{ rank }}</p>
    </div>
</template>
<script>
export default {
    data(){
        return {
            rank: null
        }
    },
    props: {
        score: Number
    },
    mounted(){
        if(this.score < 250) {
            this.rank = "You're quick!"
        } else if(this.score < 400) {
            this.rank = "Not bad!"
        } else {
            this.rank = "You're slow.."
        }
    }
}
</script>

<style scoped>
.result{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    border: 1px solid white;
    width: 400px;
    height: 200px;
    border-radius: 5px;
    margin-top: 10px;
}
</style>