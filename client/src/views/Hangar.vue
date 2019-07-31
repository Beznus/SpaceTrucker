<template>
  <v-layout
  wrap
  >
    <HangarMenu />
    <v-flex>
      <HangarContent />
    </v-flex>
  </v-layout>
</template>

<script>
import HangarMenu from '../components/HangarMenu'
import HangarContent from '../components/HangarContent'
export default {
  components: {
    HangarMenu,
    HangarContent
  }
};
</script>
