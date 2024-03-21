<template>
  <v-app id="inspire">
    <v-system-bar>
      <v-spacer></v-spacer>

      <v-icon>mdi-square</v-icon>

      <v-icon>mdi-circle</v-icon>

      <v-icon>mdi-triangle</v-icon>
    </v-system-bar>

    <v-navigation-drawer v-model="drawer">
      <v-sheet
          class="pa-4"
          color="grey-lighten-4"
      >
        <v-avatar
            class="mb-4"
            color="grey-darken-1"
            size="64"
        ></v-avatar>

        <div>john@google.com</div>
      </v-sheet>

      <v-divider></v-divider>

      <v-list>
        <v-list-item
            v-for="[icon, text] in links"
            :key="icon"
            :prepend-icon="icon"
            :title="text"
            link
        ></v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <!-- Replace HelloWorld with Inbox component -->
      <Inbox :messages="messages" />
    </v-main>
  </v-app>
</template>

<script setup>
import { ref } from 'vue'

const messages = ref([
  { title: 'Message 1', content: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit.' },
  { title: 'Message 2', content: 'Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.' },
  // Add more messages as needed
])

const drawer = ref(null)
</script>

<script>
import Inbox from './components/Inbox.vue'

export default {
  data: () => ({
    drawer: null,
    links: [
      ['mdi-inbox-arrow-down', 'Inbox'],
      ['mdi-send', 'Send'],
      ['mdi-delete', 'Trash'],
      ['mdi-alert-octagon', 'Spam'],
    ],
  }),
  components: {
    Inbox
  },
  setup() {
    return { messages }
  }
}
</script>
