<template>
  <main>
      <label for="">What is your name?
        <input 
          type="text" 
          v-model="newName" 
          placeholder="" 
        />
      </label>
      <label for="">How did you lose the game?
        <textarea 
          name="description" 
          id="description" 
          v-model="newDescription" 
          cols="30" 
          rows="10"
        ></textarea>
    </label>   
    <button @click="pushLoss">
      Share
    </button>  
    <div v-for="loss in losses" :key="loss.id">
      <h2>{{ loss.name }}</h2>
      <strong><p>{{ loss.description }}</p></strong>
    </div>
  </main>
</template>

<script>

export default {
  name: 'App',

  data() {
    return {

      newName: "",
      newDescription: "",

      losses: [
      { id: 1, name: "", description: "" },
      ],

    }
  },

  methods: {
    pushLoss() {
      this.losses.push({id: this.losses.length + 1, name: this.newName, description: this.newDescription })
      this.newName = "";
      this.newDescription = "";
    },
  }
}



// let newName = "";
// let newDescription = "";
// const posts = [
//   { id: 1, name: "Kenny", description: "I lost the game on the train." },
// ];

// This starter template is using Vue 3 experimental <script setup> SFCs
// Check out https://github.com/vuejs/rfcs/blob/script-setup-2/active-rfcs/0000-script-setup.md
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

button {
  width: 80px;
  height: 35px;
}

input,
textarea {
  max-width: 600px;
  padding:.5rem;
}


label {
  display:flex;
  flex-direction:column;
  gap:1rem;
  margin-bottom:2rem;
}

li {
  list-style: none;
}

main {
  padding:2rem;
}


</style>
