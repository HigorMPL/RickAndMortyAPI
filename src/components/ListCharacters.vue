<script setup>
const props = defineProps(["character"]);
const characterId = props.character.id;
const imageUrl = "https://rickandmortyapi.com/api/character/avatar/"+ characterId +".jpeg";

</script>

<template>
  <div class="col-md-4 mb-4">
    <div class="card">
      <img :src="imageUrl" height="100%" alt="..." class="card-img-top mt-3">
      <div class="card-body">
        <h5 class="text-center">{{ props.character.name }}</h5>
        <p class="text-center">
          <strong>Status:</strong> {{ props.character.status }}<br>
          <strong>Espécie:</strong> {{ props.character.species }}<br>
          <strong>Gênero:</strong> {{ props.character.gender }}<br>
          <strong>Localização atual:</strong> {{ props.character.location.name }}<br>
          <strong>Episódios:</strong> {{ props.character.episode.length }}
        </p>
      </div>
    </div>
  </div>
</template>

<style>

.card {
  padding: 0px 12px 0px;
  text-align: center;
}
</style>
