<template>
    <div class="chatbox">
        <p v-for="(message, i) in history" :key="i"> {{message}}</p>
    </div>
</template>

<script>
export default {
    name: 'Chatbox',
    data: () => {
        return {
            history: []
        }
    },
    props: {
        message: String
    },
    computed: {
        myArray() {
            return this.history;
        }
    },
    watch: {
        message(newMessage) {
            console.log(this.history);
            this.history.push(newMessage);
            console.log(this.history);
        }
    }
}
</script>
    
<style>
    .chatbox {
        height: 90%;

        display: flex;
        flex-direction: column;
        justify-content: flex-end;

        font-size: 1.4em;
        overflow: hidden;
    }

    .chatbox p {
        padding: 0 10px;
        margin: 2px 0;
        text-align: left;

    }
</style>