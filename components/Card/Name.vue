<template>     
      <div  
        class="card">
        <h4>{{ name }}</h4>
        <p @click="removeName">X</p>
      </div>   
</template>
<script setup lang="ts">
interface NameProps {
    name: string,
    index: number,
}
const props = defineProps<NameProps>();

const emit = defineEmits(["remove"])

const removeName = () => {
    emit("remove", props.index)
}

</script>

<style scoped>
.card{
  background-color: rgb(27, 60, 138);
  width: 15%;
  color: yellow;
  border-radius: 1rem;
  padding: 0.3rem;
  margin-right: 0.5rem;
  margin-bottom: 1rem;
  position: relative;
}
.card p{
  position: absolute;
  top: -15%;
  right:7%;
  color:rgb(0, 255, 255, 0.5);
}
</style>
