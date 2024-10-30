<template>
    <div class="card">
        <h2>{{ props.content.name }}</h2>
        <p>{{ props.content.id }}</p>
    </div>
</template>
  
<script lang="ts" setup>
    import { defineProps } from 'vue';

    const props = defineProps(['content'])

</script>
  
<style scoped>
    .card {
        background-color: aquamarine;
        border-radius: 10px;
        padding: 10px;
        display: flex;
        flex-direction: column;
        width: 350px;
        margin: 10px;
        justify-content: space-around;
    }
</style>
  