<template>
  <div class="sidebar">
    <Logo v-if="!darkTheme" class="sidebar__logo" />
    <LogoGradient v-else class="sidebar__logo" />
    <div class="sidebar__nav">
      <router-link to="/search" id="search" class="sidebar__item">
        <feather class="sidebar__item-icon" type="search"></feather>
      </router-link>
      <router-link to="/download" id="download" class="sidebar__item">
        <feather class="sidebar__item-icon" type="folder"></feather>
      </router-link>
    </div>
    <router-link to="/settings" id="settings" class="sidebar__item">
      <feather class="sidebar__item-icon" type="settings"></feather>
    </router-link>
  </div>
</template>

<style lang="scss">
@import "./Sidebar.scss";
</style>

<script>
import { mapState } from "vuex";

import Logo from "@/assets/images/Logo.svg";
import LogoGradient from "@/assets/images/LogoGradient.svg";

export default {
  components: { Logo, LogoGradient },
  computed: {
    ...mapState("darkTheme", ["darkTheme"]),
  },
};
</script>
