<template>
  <div>
    <h3>
      {{ title }}
    </h3>
    <!-- for each add text add delete button  -->
    <button @click="$emit('delete-item')">Delete</button> 
  </div>
</template>

<script>
export default {
  props: ['title']
}
</script>
<!-- scoped style jsut for this html area -->
<style  scoped> 
h3 {
  display: inline-block;
  margin: 10px;
}
</style>