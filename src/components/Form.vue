<template>
    <form>
        <input v-model="message" type="text"/>
        <button @click="handleSending">Send</button>
    </form>
</template>

<script>
export default {
    name: 'Form',
    data: () => {
        return {
            message: ""
        }
    },
    methods: {
        handleSending: function(event) {
            event.preventDefault();
            if(this.message != "") {
                this.emitMessage();
            }
            this.message = "";
        },
        emitMessage: function() {
            this.$emit('emitMessage', this.message);
        }
    }
}

</script>

<style scoped>
    form {
        height: 5%;
        display: flex;

    }

    form input {
        background-color: transparent;
        border: 1px solid #333333;
        flex-grow: 2;
        padding-left: 10px;
    }

    form button {
        flex-grow: .3;
    }
</style>