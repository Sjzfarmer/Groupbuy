<template>  
    <div>  
      <h1>留言板</h1>  
      <form @submit.prevent="addMessage">  
        <label for="name">姓名:</label>  
        <input type="text" id="name" v-model="name" required>  
        <br>  
        <label for="message">留言:</label>  
        <textarea id="message" v-model="message" required></textarea>  
        <br>  
        <button type="submit">提交</button>  
      </form>  
      <ul>  
        <li v-for="(message, index) in messages" :key="index">  
          <strong>{{ message.name }}</strong>: {{ message.content }}  
        </li>  
      </ul>  
    </div>  
  </template>  
    
  <script>  
  export default {  
    data() {  
      return {  
        name: '',  
        message: '',  
        messages: []  
      };  
    },  
    methods: {  
      addMessage() {  
        this.messages.push({ name: this.name, content: this.message });  
        this.name = '';  
        this.message = '';  
      }  
    }  
  };  
  </script>