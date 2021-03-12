<template>
  <div id="app">
    <a-button @click="status.modalVisible=true">打开dialog</a-button>
    <a-modal width="70%"
             :dialog-style="{ top: '20px' }"
             :mask-closable="false"
             :visible="status.modalVisible"
             @cancel="status.modalVisible=false;status.loading=false">
      <template #footer>
        <a-button @click="status.modalVisible=false">取消</a-button>
        <a-button type="primary" @click="status.loading=true" :loading="status.loading">解析</a-button>
      </template>
    </a-modal>
  </div>
</template>

<script>

import { reactive } from '@vue/composition-api';

export default {
  name: 'App',
  setup() {
    const status = reactive({
      modalVisible: false,
      loading: false
    })
    return {
      status
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
