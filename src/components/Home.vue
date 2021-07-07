<template>
  <h1>Testing Router</h1>
  <p>{{ name }}</p>
  <input v-model="newName" type="text">
  <button @click="saveName" >Save</button>
</template>

<script setup >
import { computed, ref } from "vue";
import { useStore } from "vuex";

const store = useStore();
const name = computed(() => {
  return store.state.user.name;
});

const newName = ref('')
function saveName() {
    store.dispatch('saveName', newName.value)
    newName.value = ''
}
</script>
