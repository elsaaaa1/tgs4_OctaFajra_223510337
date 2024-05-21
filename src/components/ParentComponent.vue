<template>
    <div class="parent-container">
      <h2>Parent Component</h2>
      <ChildComponent @childData="handleChildData">
        <template v-slot:nestedData>
          <p>ini data dari ParentComponent slot.</p>
        </template>
      </ChildComponent>
      <div class="data-display">
        <p>Data from Child Component: <strong>{{ parentData }}</strong></p>
      </div>
    </div>
  </template>
  
  <script>
  import ChildComponent from './ChildComponent.vue';
  
  export default {
    components: {
      ChildComponent
    },
    data() {
      return {
        parentData: ''
      };
    },
    methods: {
      handleChildData(data) {
        this.parentData = data;
      }
    }
  };
  </script>
  
  <style scoped>
  .parent-container {
    border: 1px solid #ccc;
    padding: 20px;
    border-radius: 5px;
    background-color: #f9f9f9;
    max-width: 600px;
    margin: 0 auto;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  
  h2 {
    color: #34495e;
  }
  
  .data-display {
    margin-top: 20px;
    padding: 10px;
    border: 1px solid #ddd;
    background-color: #fff;
    border-radius: 5px;
  }
  </style>
  