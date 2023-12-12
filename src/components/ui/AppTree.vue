<template>
  <div class="outer">
    <p class="label" @click="toggleHideShow">
      <span v-if="nodes">{{ !hideShow ? "▶" : "▼" }}</span>
      {{ props.label }}
    </p>
    <div class="child" v-if="hideShow">
      <app-tree
        v-for="(item, index) in nodes"
        :key="index"
        :label="item.label"
        :nodes="item.nodes"
      ></app-tree>
    </div>
  </div>
</template>

<script setup>
import { defineProps, ref } from "vue";

const hideShow = ref(false);

const toggleHideShow = () => {
  hideShow.value = !hideShow.value;
};

const props = defineProps({
  label: String,
  nodes: Array,
});
</script>

<style scoped>
.label {
  display: flex;
  align-items: center;
  gap: 5px;
  user-select: none;
  cursor: pointer;
}
.child {
  margin-left: 10px;
  padding-left: 10px;
  border-left: 2px solid grey;
}
</style>
