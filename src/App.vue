<template>
  <div id="app">
    <div class="container">
      <h1>Workshop #1 Limit Message</h1>
      <div class="input-group" >
        <div class="input-group-prepend">
          <span class="input-group-text" v-text="max - message.length"></span>
        </div>
          <input type="text" class="form-control" v-model="message" :maxlength="max"/>
        </div>
    
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data(){
    return {
      message:"",
      max:20
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
