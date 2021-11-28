<template>
  <header class="p-1">
    <img src="../assets/logo.png" alt="">
    <select v-model="generes" @change="$emit('performSearch', generes)">
      <option value="">All generes</option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
    </select>
  </header>
</template>

<script>
export default {
    name: 'Header',
    data() {
      return {
        generes: '',
      }
    },

}
</script>

<style scoped lang="scss">
@import '@/styles/variables';

    header {
        background: $bg-sec-col;

        img {
            height: 3rem;
        }
    }

</style>