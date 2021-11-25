<template>
  <div class="card text-center h-100">
        <img :src="image" :alt="title">
        <div class="p-3">
            <h4>{{ title }}</h4>
            <div class="sub-title">{{ subTitle }}</div>
            <div class="sub-title h6 my-2">{{ subTitle2 }}</div>
            <div class="text">{{ text }}</div>
        </div>
  </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        image: String,
        title: String,
        subTitle: String,
        subTitle2: String,
        text: String,

    }
}
</script>

<style scoped lang="scss">
@import '@/styles/variables';

    .card {
        background: #2e3a46;

        .sub-title {
            color: #818584;
        }

        
    }
</style>