<script setup>
console.log('BaseLayout setup');
const links = [
  'Dashboard',
  'Messages',
  'Profile',
  'Updates',
]
</script>

<template>
  <div>
    <v-app-bar flat>
      <v-container class="mx-auto d-flex align-center justify-center">
        <v-avatar class="me-4 " color="grey-darken-1" size="32"></v-avatar>
        <v-btn v-for="link in links" :key="link" :text="link" variant="text"></v-btn>
        <v-spacer></v-spacer>
        <v-responsive max-width="160">
          <v-text-field density="compact" label="Search" rounded="lg" variant="solo-filled" flat hide-details
            single-line></v-text-field>
        </v-responsive>
      </v-container>
    </v-app-bar>
    <v-main class="bg-grey-lighten-3">
      <v-container>
        <v-row>
          <v-col cols="2">
            <v-sheet rounded="lg">
              <v-list rounded="lg">
                <v-list-item v-for="n in 5" :key="n" :title="`List Item ${n}`" link></v-list-item>
                <v-divider class="my-2"></v-divider>
                <v-list-item color="greyj-lighten-4" title="Refresh" link></v-list-item>
              </v-list>
            </v-sheet>
          </v-col>
          <v-col>
            <v-sheet min-height="70vh" rounded="lg">
              <NuxtPage />
            </v-sheet>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </div>
</template>
