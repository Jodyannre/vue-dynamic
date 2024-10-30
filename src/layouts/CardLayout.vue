<template>
    <h1> Card Layout </h1> 
    <div class="container"> 
        <UserCard v-for="user in content" :key="user.id" :content="user"/>
    </div>
</template>
  
<script lang="ts" setup>
    import { ref, defineProps } from 'vue'
    import UserCard from '@/components/UserCard.vue';

    const props = defineProps(['content']);
</script>
  
<style scoped>
    .container {
        width: 100vw;
        display: flex;
        align-items: flex-start;
        justify-content: space-around;
        flex-wrap: wrap;
    }
</style>
  