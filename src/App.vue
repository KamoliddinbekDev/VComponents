<template>
  <div>
    <AppTree :label="data.label" :nodes="data.nodes" />
  </div>
</template>

<script setup>
import AppTree from "@/components/ui/AppTree.vue";
import { ref } from "vue";

const data = ref({
  label: "categories",
  nodes: [
    {
      label: "Models",
      nodes: [
        {
          label: "Data warehouse",
          nodes: [{ label: "Report samples" }, { label: "Sales performance" }],
        },
      ],
    },
    {label: "Statics"}
  ],
});
</script>

<style>
#app {
  font-family: monospace, Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
