<script setup>
  import {onMounted, onUpdated, ref} from 'vue'
  const count = ref(0);
  
  onMounted(() => {
    console.log(count.value);
  })

  const whenClick = () =>{
    console.log(count.value);
    count.value++;
  }
  onUpdated(()=>{
    console.log(count.value);
  })
  onUpdated(()=>{
    console.log("hello world");
  });
</script>

<template>
  <div>
    <button @click="whenClick">{{ count }}</button>
    <div>{{ htmlString }}</div>
    <div v-html="htmlString"></div>
  </div>
</template>