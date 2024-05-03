<script setup>
  import { onMounted, reactive, ref } from 'vue';
  import ListCharacters from '../components/ListCharacters.vue';

  let characters = reactive(ref([]));

  onMounted(() => {
    fetch("https://rickandmortyapi.com/api/character")
    .then(response => response.json())
    .then(data => {
      characters.value = data.results.slice(0, 18);
    })
  });
</script>

<template>
  <main>
    <div class="container">
      <div class="row justify-content-center mt-4">
          <div class="card" style="width: 100%;">
            <div class="card-body row justify-content-around">
              <ListCharacters 
                v-for="character in characters"
                :key="character.id"
                :character="character"
              />
            </div>
          </div>
      </div>
    </div>
  </main>
</template>
