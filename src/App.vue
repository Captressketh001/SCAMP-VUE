<template>
  <header>
    <div class="logo">dyco.learn</div>
    <div 
      v-for="tab in tabs"
      :key="tab"
      :class="['items', {active:currentTab === tab}]"
      @click="currentTab = tab"
    >
    {{tab}}
    </div>
  </header>
  <main>
   <keepalive> <component :is="currentTab"></component></keepalive>
  </main>
</template>

<script>
import Intro from './components/Intro.vue'
import CodeExample from './components/CodeExample.vue'
import Reference from './components/Reference.vue'

export default {
  name: 'App',
  components: {
    Intro, CodeExample, Reference
  },
  data (){
    return{
      currentTab:'Intro',
      tabs:['Intro', 'CodeExample', 'Reference']
    }
  }
}
</script>

<style scoped>
  
</style>
