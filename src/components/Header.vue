<template>
  <div class="p-3 d-flex justify-content-between">
      <img src="../assets/logo.png" alt="Logo">
      <select 
            v-model="Choice"
            class="my-2" 
            name="generi"
            @change="$emit('userselection', Choice)"
            >
            <option value="tutti">Tutti i Generi</option>
            <option v-for="(element, index) in genreList" :key="`genre-${index}`"
            >{{ element }}
            </option>
      </select>
  </div>
</template>

<script>
export default {
name: 'Header',

props: {
    genreList: Array,
},

data(){
    return {
        Choice:'',
    }
},
}
</script>

<style scoped lang="scss">

div {
    img {
        width: 50px;
        }
    background-color: #2E3A46;
    select{
        color: white;
        background-color: #2E3A46;
        border: 1px solid white;
        width: 150px;
    }
}
</style>