<template>
  <div id="Work2">
    <div class="container">
      <h1>Workshop #2 Preview Image</h1>
      <hr>
      <div v-if="!image">
        <input type="file" class="form-control" @change="onFileChange" />
        <hr>
      </div>
     <div v-else >
        <img :src="image" class="img-fluid" alt="" /> <hr>
        <button class="btn btn-danger" @click="removeImage">Remove</button>
     </div>
      
    </div>
  </div>
</template>
  
  <script>
export default {
  name: "Work2",
  data() {
    return {
        image : ""
    }
  },
  methods:{
    onFileChange: function(e){
        let files = e.target.files
        if(!files.length)
        return
        this.createImage(files[0]);
    },
    createImage(files){
        let reader = new FileReader();
        reader.onload = (e) => {
            this.image = e.target.result;
        }
        reader.readAsDataURL(files);
    },
    removeImage(){
        this.image = "";
    }

  }
};
</script>
  
  <style>
#Work2 {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
  