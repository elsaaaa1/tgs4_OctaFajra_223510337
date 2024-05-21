<template>
    <div class="child-container">
      <h3>Child Component</h3>
      <input v-model="childInput" placeholder="Enter data here" />
      <button @click="sendToParent">Send to Parent</button>
      <NestedChildComponent @nestedChildData="emitToParent" />
      <slot name="nestedData"></slot>
    </div>
  </template>
  
  <script>
  import NestedChildComponent from './NestedChildComponent.vue';
  
  export default {
    components: {
      NestedChildComponent
    },
    data() {
      return {
        childInput: ''
      };
    },
    methods: {
      sendToParent() {
        this.$emit('childData', this.childInput);
      },
      emitToParent(data) {
        this.$emit('childData', data);
      }
    }
  };
  </script>
  
  <style scoped>
  .child-container {
    border: 1px solid #aaa;
    padding: 15px;
    border-radius: 5px;
    background-color: #e9e9e9;
    margin-top: 20px;
  }
  
  h3 {
    color: #2c3e50;
  }
  
  input {
    padding: 10px;
    margin-bottom: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    width: calc(100% - 22px);
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
  