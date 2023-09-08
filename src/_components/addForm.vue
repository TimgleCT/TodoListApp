<script setup>
  import { ref } from 'vue';

  const addInputString = ref('');
  const emits = defineEmits(['addText']);
  
  function clickAddBtn(){
    if(addInputString.value !== ''){
      emits('addText', addInputString.value);
      addInputString.value = '';
    }
  }
</script>

<template>
    <form class="px-10 py-12 bg-white shadow-sm">
        <section class="flex">
          <input v-model="addInputString" type="text" placeholder="做點重要的事吧..." class="w-full text-2xl focus:outline-none input-lg input input-bordered" />
          <button @click.prevent.self="clickAddBtn()" class="text-xl btn-lg btn btn-neutral">新增</button>
        </section>
    </form>
</template>

<style scoped></style>