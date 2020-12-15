<template>
  <div id="app">
    <Chatbox :message="messageToPrint"/>
    <WrittingBox :active="writtingStatus"/>
    <Form @emitMessage="handleMessageSending"/>
  </div>
</template>

<script>
import Chatbox from './components/Chatbox.vue';
import WrittingBox from './components/WrittingBox.vue'
import Form from './components/Form.vue';

export default {
  name: 'App',
  components: {
    Chatbox,
    WrittingBox,
    Form
  },
  data: () => ({
    messageToPrint: "",
    writtingStatus: false
  }),
  methods: {
    handleMessageSending: function(message) {
      this.printMessage(message);

      this.toggleWrittingVisibility();
      //const response = this.getBotResponse(message);
      //this.printMessage(response);
      this.toggleWrittingVisibility();
    },
    printMessage: function(message) {
      this.messageToPrint = message;
    },
    toggleWrittingVisibility: function() {
      this.writtingStatus ? this.writtingStatus = false : this.writtingStatus = true;
    },
    getBotResponse: function(message) {
      console.log(message);
      //return fetch()
      return message;
    } 
  }
}

</script>

<style>
  .html, body {
    margin: 0;
    padding: 0;
  }

  body {
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;

    background-color: #eaeaea;
  }

  #app {
    font-family: 'Lato', sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    padding: 15px;
    border-radius: 25px;

    width: 50vw;
    height: 75vh;
    background-color: #ffffff;
    box-shadow: 0px 0px 10px 2px rgba(102,102,102,0.6);
  }
</style>
