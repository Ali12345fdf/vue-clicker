<script>
export default {
props:["counter"],
methods:{
  
}
}
</script>


<template>
  <div class="box1" @click="$emit('counterEmmet')">{{ inputTime }} секунд</div>
</template>



<style>

</style>