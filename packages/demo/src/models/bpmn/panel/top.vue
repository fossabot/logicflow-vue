<template>
  <h1>流程属性</h1>
  <a-tabs>
    <a-tab-pane key="general" tab="常规">
      <a-form layout="vertical" class="properties-panel-form" :model="data" name="ppform">
        <a-form-item label="编号">
          <a-input v-model:value="data.id" />
        </a-form-item>
        <a-form-item label="名称" name="text">
          <a-textarea v-model:value="data.text" auto-size />
        </a-form-item>
      </a-form>
    </a-tab-pane>
    <a-tab-pane key="extensions" tab="高级">
      <a-form
        layout="vertical"
        class="properties-panel-form"
        :model="data.properties"
        name="propsform"
      >
        <a-form-item label="属性" name="properties">
          <properties-editor :value="data.properties" />
        </a-form-item>
      </a-form>
    </a-tab-pane>
  </a-tabs>
</template>

<script setup lang="ts">
import { usePropertiesPanelData } from 'logicflow-useapi';
import './style.css';

const data = usePropertiesPanelData(true);
</script>
