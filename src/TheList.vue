<template>
  <div class="list-container">
    <div class="heading">
      <h2>{{title}}</h2>
      <button @click="toggleOpen">
        <span v-if="isOpen">&or;</span>
        <span v-else>&and;</span>
      </button>
    </div>

    <slot :isOpen="isOpen" :displayItems="displayItems"></slot>

    <button @click="isCollapsed = !isCollapsed">
      {{isCollapsed ? `Show all ${items.length}` : "Show less"}}
    </button>
  </div>
</template>

<script setup>
import { computed, ref, defineProps } from 'vue';

const props = defineProps({
  title: String,
  items: Array
})

const isOpen = ref(true)
const isCollapsed = ref(false)

const displayItems = computed(() => isCollapsed.value ? props.items.slice(0, 3) : props.items)

function toggleOpen() {
  isOpen.value = !isOpen.value
  isCollapsed.value = false
}

</script>
