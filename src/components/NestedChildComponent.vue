<template>
    <div class="nested-child-container">
      <h4>Nested Child Component</h4>
      <button @click="sendDataToChild">Send Data to Child</button>
    </div>
  </template>
  
  <script>
  export default {
    methods: {
      sendDataToChild() {
        this.$emit('nestedChildData', 'Hai from Nested Child Component');
      }
    }
  };
  </script>
  
  <style scoped>
  .nested-child-container {
    border: 1px solid #888;
    padding: 10px;
    border-radius: 5px;
    background-color: #d9d9d9;
    margin-top: 10px;
  }
  
  h4 {
    color: #2c3e50;
  }
  
  button {
    padding: 10px;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #0056b3;
  }
  </style>
  