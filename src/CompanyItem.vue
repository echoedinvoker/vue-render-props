<template>
  <li class="company" @mouseenter="isVisible = true" @mouseleave="isVisible = false">
      <p className="company-name">{company.companyName}</p>
        <p className="company-phrase" v-if="isVisible">
      <strong>About:</strong> {{company.phrase}}
        </p>
    </li>
</template>

<script setup>
import { ref, defineProps } from 'vue';

const props = defineProps({
  company: Object,
  defaultVisibility: Boolean
})
const isVisible = ref(props.defaultVisibility)
</script>
