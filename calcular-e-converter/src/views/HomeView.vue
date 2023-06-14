<template>
  <section>
    <CssUnits />
  </section>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import CssUnits from "../components/CssUnits/index.vue";
export default defineComponent({
  name: "HomeView",
  components: {
    CssUnits,
  },
});
</script>
