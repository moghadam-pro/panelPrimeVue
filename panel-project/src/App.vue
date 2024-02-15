<script setup>
import {ref} from 'vue';
import {useToast} from "primevue/usetoast";

const text = ref()
const toast = useToast();
const greet = () => {
  toast.add({severity:'success', summary: 'PrimeVue JS', detail: text.value})
}
</script>

<template>
  <Toast></Toast>
  <div class="container">
    <span class="p-float-lable">
      <InputText id="txt" type="text" v-model="text"/>
      <label for="txt">Text</label>
    </span>
    <Button label="Greet" @click="greet" icon="pi pi-user"></Button>
    <div class="card flex justify-content-center">
    <Sidebar v-model:visible="visible" header="Sidebar">
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
    </Sidebar>
    <Button icon="pi pi-arrow-right" @click="{visible = true}"></Button>
</div>
  </div>
</template>



<style scoped>
.container{
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
}
</style>
