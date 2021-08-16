<template>
  <v-app-bar color="transparent" app flat dense absolute height="55rem">
    <v-app-bar-nav-icon
      @click="$emit('open-drawer')"
      style="margin-top: 0.5rem"
    />
    <v-toolbar-title>
      <!-- search section -->
      <v-form>
        <v-text-field
          label="Search..."
          name="Search"
          prepend-icon="mdi-magnify"
          type="text"
          class="search"
        />
      </v-form>
    </v-toolbar-title>
    <v-spacer></v-spacer>
    <!-- notification section -->
    <v-toolbar-items class="shrink mt-1 hidden-sm-and-down">
      <v-col>
        <v-icon class="mr-5">mdi-bell</v-icon>
        <v-icon class="mr-5">mdi-help-circle</v-icon>
        <v-icon>mdi-account</v-icon>
      </v-col>
    </v-toolbar-items>
    <hr />
  </v-app-bar>
</template>
<script></script>
<style scoped>
.search {
  width: 50rem;
  margin-top: 1.2rem !important;
}
</style>
