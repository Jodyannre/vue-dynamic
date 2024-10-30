<template>
  <h1> Lista de usuarios </h1>
  <input type="text" v-model="search" placeholder="Buscar usuario" @keyup="handleSearch"/>
  <div>
    <button @click="handleLayoutChange(TableLayout)"> Ver datos en tabla</button>
    <button @click="handleLayoutChange(ListLayout)"> Ver datos en lista</button>
    <button @click="handleLayoutChange(CardLayout)"> Ver datos en tarjetas</button>
    <component v-bind:is="layout" :content="filteredUsers"/>
</div>
</template>

<script lang="ts" setup>
  import { ref, defineAsyncComponent } from 'vue';

  const ListLayout = defineAsyncComponent(()=> import('@/layouts/ListLayout.vue'));
  const TableLayout = defineAsyncComponent(()=> import('@/layouts/TableLayout.vue'));
  const CardLayout = defineAsyncComponent(()=> import('@/layouts/CardLayout.vue'));

  const layout = ref(ListLayout);

  const search = ref('');

  const handleSearch = () => {
    filteredUsers.value = users.value.filter(user => user.name.toLowerCase().includes(search.value.toLowerCase()));
  }

  const handleLayoutChange = (cmp) => layout.value = cmp; 

  const users = ref([
    {
      id: 1,
      name: 'John Doe',
    },
    {
      id: 2,
      name: 'Jane Doe',
    },
    {
      id: 3,
      name: 'John Smith',
    },
    {
      id: 4,
      name: 'Jane Smith',
    }
  ]);

  const filteredUsers = ref([]);

  filteredUsers.value = users.value;

  /* con option API es asi

  import { ref, defineAsyncComponent } from 'vue';
  import ListLayout from '@/layouts/ListLayout.vue';
  import TableLayout from '@/layouts/TableLayout.vue';
  import CardLayout from '@/layouts/CardLayout.vue';

  export default defineComponent {
    data(){},
    methods: {}
    components: {
      ListLayout,
      TableLayout,
      CardLayout
    }
  }
  */
</script>