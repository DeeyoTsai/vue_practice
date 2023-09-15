<script setup>
import deviceInfo from '@/components/info.vue';
import deviceItem from '@/components/item.vue';
import { v4 as uuidv4 } from 'uuid';
import { ref, reactive } from "vue";


const title = "AUO";
const device = ref('');
const devices = reactive([]);


const addDevice = () => {
      if (device.value !== ""){
        const item = {
          id:uuidv4(),
          title:device.value,
        };
        devices.unshift(item);
        device.value = "";
      };
    };
const removeDevice = (id) => {
      // console.log(id);
      const index = devices.findIndex((e) => {
          return e.id === id;
        });
      // console.log(index);
      devices.splice(index,1);
    };

</script>

<template>

  <h1 class="my-6 text-4xl font-extrabold"> {{ title }} 設備管理系統 </h1>
  <form>
    <label class="p-2 text-white bg-black">設備名稱</label><br>
    <div class="flex gap-2 items-center">
      <input
            type="text"
            placeholder="請輸入設備名稱"
            class="input-device"
            v-model="device"
      />
      <button @click.prevent="addDevice" class="btn btn-action">新增</button>
    </div>
  </form>
  <section>

    <deviceInfo v-bind:devices="devices" />

    <deviceItem @remove-auo-item="removeDevice" 
                v-for="d in devices" 
                :it="d" 
    />

  </section>

</template>

<style scoped>
.input-device {
  @apply my-2 px-2 py-2 text-xl border border-slate-500;
}
.btn {
  @apply mx-1 py-2 px-4 select-none;
}
.btn-action {
  @apply bg-black text-white hover:bg-slate-600;
}
</style>
