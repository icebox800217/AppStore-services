<template>
  <AppHeader fixed>
    <SidebarToggler class="d-lg-none" display="md" mobile />
    <!-- <SidebarToggler class="d-md-down-none" display="lg" :defaultOpen="true" /> -->
    <b-navbar-nav class="d-md-down-none">
      <b-nav-item class="px-3" to="/users" exact>Users</b-nav-item>
      <b-nav-item class="px-3">Settings</b-nav-item>
      <b-nav-item class="px-3">Settings2</b-nav-item>
      <b-nav-item class="px-3">Settings3</b-nav-item>
    </b-navbar-nav>
    <b-navbar-nav class="ml-auto">
      <DefaultHeaderDropdownAccnt />
    </b-navbar-nav>
  </AppHeader>
</template>
<script>
import { Header as AppHeader, SidebarToggler, AsideToggler } from "@coreui/vue";
import DefaultHeaderDropdownAccnt from "./DefaultHeaderDropdownAccnt";

export default {
  name: "DefaultHeader",
  components: {
    AsideToggler,
    AppHeader,
    DefaultHeaderDropdownAccnt,
    SidebarToggler
  }
};
</script>
