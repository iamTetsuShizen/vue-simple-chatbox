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
            this.history.push(newMessage);
        }
    }
}
</script>
    
<style>

</style>