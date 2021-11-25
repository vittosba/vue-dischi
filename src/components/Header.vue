<template>
  <header class="p-1">
    <img src="../assets/logo.png" alt="">
  </header>
</template>

<script>
export default {
    name: 'Header',

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