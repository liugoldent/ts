<template>
  <div class="home">
    <input v-model="ParString">
    <!-- <button @click="fetchData(ParString)">toUpper</button> -->
    <h1>{{ParString}} </h1>
  </div>
</template>
<script lang="ts">
import { defineComponent, computed } from '@vue/composition-api'

export default defineComponent({
  setup () {
      let ParString:string = 'Hello World';

      /**
       * @description 大寫
       */
      const fetchData = function(Par:String): string{
          console.log('Par',Par);
          return Par.toUpperCase()
      };

      let UpperData:string = fetchData(ParString);

      return {
          //0717
          ParString,
          fetchData,
          UpperData,

          //0724
      }
  }
});
</script>
