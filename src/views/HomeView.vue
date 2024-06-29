<template>
  <MainHeader/>
  <div class="home">
    <HelloWorld/>
  </div>
  <MainFooter/>
</template>

<script setup lang="ts">
import MainHeader from '@/components/MainHeader.vue';
import MainFooter from '@/components/MainFooter.vue';
import { defineComponent } from 'vue';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src
</script>

<style>
  .home {

    background-color: blue;
  }
</style>