<template>
    <div class="list">
        <h2>{{ props.content.name }}</h2>
        <p>{{ props.content.id }}</p>
    </div>
</template>
  
<script lang="ts" setup>
    import { defineProps } from 'vue';

    const props = defineProps(['content'])

</script>
  
<style scoped>
    .list {
        background-color: aquamarine;
        border-radius: 10px;
        padding: 10px;
        display: flex;
        width: 100%;
        margin: 10px;
    }
</style>
  