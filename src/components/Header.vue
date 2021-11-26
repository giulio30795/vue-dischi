<template>
  <div class="p-3 d-flex justify-content-between">
      <img src="../assets/logo.png" alt="Logo">
      <select class="my-2" name="generi" id="generi">
          <option value="Pop">Pop</option>
          <option value="Pop">Rock</option>
          <option value="Pop">Jazz</option>
          <option value="Pop">Metal</option>
      </select>
  </div>
</template>

<script>
export default {
name: 'Header'
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