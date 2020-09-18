<template>
  <h1>{{ msg }}</h1>
  <button @click="count++">count is: {{ count }}</button>
  <button @click="a++">a is: {{ a }}</button>
  {{b}}
  <p>Edit <code>components/HelloWorld.vue</code> to test hot module replacement.</p>
</template>

<script>
import {ref, reactive, computed} from 'vue';
import {effect} from '@vue/reactivity'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  setup(){
    let a = ref(0);
    a.value++;
    let b = computed(() => a.value * 2);

    // effect(() => {
    //   console.log(a);
    // })
    return{a, b}
  },

  data() {
    return {
      count: 0
    }
  }
}
</script>
