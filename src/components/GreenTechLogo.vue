<template>
  <img src="@/assets/logo.png" alt="logo" display: inline-block
  :width="props.width" :height="props.height" :style="{ left :
  props.paddingLeft, top : props.paddingTop, position: 'absolute'}"/>
</template>

<script setup lang="ts">
import { withDefaults, defineProps } from "vue";

interface Props {
  width?: string;
  height?: string;
  paddingLeft?: string;
  paddingTop?: string;
}

//set default width and height here but allow the user to pass alternative args if needed
const props = withDefaults(defineProps<Props>(), {
  width: "122.83px",
  height: "40px",
  paddingLeft: "35px",
  paddingTop: "30px",
});
</script>

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "GreenTechLogo",
});
</script>
