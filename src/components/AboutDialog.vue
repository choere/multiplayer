<template>
  <VDialog v-model="dialog" max-width="400">
    <VCard>
      <VCardTitle>About</VCardTitle>
      <VCardText class="text-center">
        <p>Multi track player</p>
        <p>Version {{ version }}</p>
      </VCardText>
    </VCard>
  </VDialog>
</template>

<script>
export default {
  data() {
    return {
      version: process.env.PACKAGE_VERSION
    };
  },
  computed: {
    dialog: {
      get() {
        return this.$store.state.dialog === 'about';
      },
      set() {
        return this.$store.dispatch('toggleAboutDialog');
      }
    }
  }
};
</script>
