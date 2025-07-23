<template>
  <div class="home">
    <GreenTechLogo />
    <ThanksText />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import GreenTechLogo from "@/components/GreenTechLogo.vue";
import ThanksText from "@/components/ThanksText.vue";

//redirect back to form after 5 seconds of displaying the thank you msg
window.setTimeout(() => {
  window.location.href = "/";
}, 5000);

export default defineComponent({
  name: "HomeView",
  components: {
    ThanksText,
    GreenTechLogo,
  },
});
</script>
