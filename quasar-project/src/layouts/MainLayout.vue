<template>
  <q-layout view="lHr RpR fFf">
    <q-header bordered class="bg-white text-black">
      <q-toolbar>
        <!-- <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" /> -->

        <q-toolbar-title class="text-weight-bold"> Home </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer
      show-if-above
      v-model="leftDrawerOpen"
      side="left"
      :width="250"
      bordered
    >
      <q-icon class="q-pa-md" name="home" size="md" />

      <q-list>
        <q-item to="/" clickable v-ripple exact>
          <q-item-section avatar>
            <q-icon class="q-pa-md" size="md" name="home" />
          </q-item-section>

          <q-item-section class="text-h6 text-weight-bold">Home</q-item-section>
        </q-item>

        <q-item clickable v-ripple exact>
          <q-item-section avatar>
            <q-icon class="q-pa-md" size="md" name="search" />
          </q-item-section>
          <q-item-section class="text-h6 text-weight-bold"
            >Search</q-item-section
          >
        </q-item>

        <q-item to="/src/pages/PageNotifications.vue" clickable v-ripple exact>
          <q-item-section avatar>
            <q-icon class="q-pa-md" size="md" name="notifications" />
          </q-item-section>
          <q-item-section class="text-h6 text-weight-bold"
            >Notifications</q-item-section
          >
        </q-item>

        <q-item clickable v-ripple exact>
          <q-item-section avatar>
            <q-icon class="q-pa-md" size="md" name="mail_outline" />
          </q-item-section>
          <q-item-section class="text-h6 text-weight-bold"
            >Messages</q-item-section
          >
        </q-item>

        <q-item clickable v-ripple exact>
          <q-item-section avatar>
            <q-icon class="q-pa-md" size="md" name="list_alt" />
          </q-item-section>
          <q-item-section class="text-h6 text-weight-bold"
            >Lists</q-item-section
          >
        </q-item>

        <q-item clickable v-ripple exact>
          <q-item-section avatar>
            <q-icon class="q-pa-md" size="md" name="people" />
          </q-item-section>
          <q-item-section class="text-h6 text-weight-bold">
            Communities
          </q-item-section>
        </q-item>

        <q-item clickable v-ripple exact>
          <q-item-section avatar>
            <q-icon class="q-pa-md" size="md" name="account_circle" />
          </q-item-section>
          <q-item-section class="text-h6 text-weight-bold"
            >Profile</q-item-section
          >
        </q-item>

        <q-item clickable v-ripple exact>
          <q-item-section avatar>
            <q-icon class="q-pa-md" size="md" name="settings" />
          </q-item-section>

          <q-item-section class="text-h6 text-weight-bold"
            >Settings</q-item-section
          >
        </q-item>
      </q-list>
    </q-drawer>

    <q-drawer show-if-above v-model="right" side="right" :width="389" bordered>
      <q-input
        placeholder="Search Twitter"
        class="q-ma-md"
        outlined
        rounded
        dense
      >
        <template v-slot:prepend>
          <q-icon name="search" />
        </template>
      </q-input>

      <!-- -----------------------tabs------------------------ -->
      <div class="q-pa-md">
        <q-card class="my-card" flat bordered>
          <q-card-section>
            <div class="text-h6">Our Changing Planet</div>
            <div class="text-subtitle2">by John Doe</div>
          </q-card-section>

          <q-tabs v-model="tab" class="text-teal">
            <q-tab label="Tab one" name="one" />
            <q-tab label="Tab two" name="two" />
          </q-tabs>

          <q-separator />

          <q-tab-panels v-model="tab" animated>
            <q-tab-panel name="one">
              The QCard component is a great way to display important pieces of
              grouped content.
            </q-tab-panel>

            <q-tab-panel name="two">
              With so much content to display at once, and often so little
              screen real-estate, Cards have fast become the design pattern of
              choice for many companies, including the likes of Google and
              Twitter.
            </q-tab-panel>
          </q-tab-panels>
        </q-card>
      </div>
      <!-- ----------------------------Tabs--------------------------------------- -->
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const leftDrawerOpen = ref(false);
    const rightDrawerOpen = ref(false);

    return {
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },

      rightDrawerOpen,
      toggleRightDrawer() {
        rightDrawerOpen.value = !rightDrawerOpen.value;
      },
    };
  },
};
</script>
