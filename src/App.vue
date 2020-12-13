<template>
  <div id="app">
    <div class="container">
      <Chatbox :message="messageFromForm"/>
      <Form @emitMessage="handleMessageSending"/>
    </div>
  </div>
</template>

<script>
import Chatbox from './components/Chatbox.vue';
import Form from './components/Form.vue';

export default {
  name: 'App',
  components: {
    Chatbox,
    Form
  },
  data: () => ({
    messageFromForm: ""
  }),
  methods: {
    handleMessageSending: function(message) {
      this.sendMessage(message);
    },
    sendMessage: function(message) {
      this.messageFromForm = message;
    }
  }
}

</script>

<style scoped>
  #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

  }

  .container {
    width: 100vw;
    height: 100vh;
  }
</style>
