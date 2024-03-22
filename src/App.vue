<template>
  <v-layout class="rounded rounded-md">

    <v-navigation-drawer
      color="white"
      width="200"
    >
      <DrawerPanel></DrawerPanel>
    </v-navigation-drawer>

    <v-main class="d-flex align-center justify-center bg-grey-lighten-3" style="min-height: 100vh;">
      Main Content
    </v-main>
  </v-layout>
</template>
<script>
import DrawerPanel from "./components/DrawerPanel";
export default {
  components: {DrawerPanel}
}
</script>
