<template>
  <div class="app">
    <p>{{ name }} - {{ age }}</p>
    <button @click="changeName('Zelda')">Change Name</button>
    <button @click="changeAge(30)">Change Age</button>
  </div>
</template>

<script lang="ts">
// import { defineComponent, reactive, toRefs } from 'vue';
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'App',
  components: {},
  setup() {
    // 1. data using reactive state
    // const state = reactive({
    //   name: 'Link',
    // age: 24 as string | number, // type assertion
    // });

    // state.name = 999 // cannot change type
    // state.age = '25'

    // return { ...toRefs(state) };

    // 2. data using refs
    const name = ref('Link');
    const age = ref<number | string>(25); // defining type using generic

    age.value = '28';

    return { name, age };
  },
  methods: {
    changeName(name: string) {
      this.name = name;
      return name;
    },
    changeAge(age: string | number) {
      this.age = age;
      return age;
    },
  },
});
</script>
