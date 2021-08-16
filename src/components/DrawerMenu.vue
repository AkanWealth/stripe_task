<template>
  <v-navigation-drawer
    style="background-color: #f7fafc"
    floating
    :value="value"
    app
    @input="$emit('input', $event)"
    :width="270"
  >
    <v-list>
      <v-list-group :value="true" prepend-icon="mdi-store">
        <template v-slot:activator>
          <v-list-item-title class="store">Store Name</v-list-item-title>
        </template>
        <v-list-item>
          <v-list-item-icon>
            <v-icon>mdi-home</v-icon>
          </v-list-item-icon>

          <v-list-item-title
            ><router-link style="text-decoration: none; color: inherit" to="#"
              >Home</router-link
            ></v-list-item-title
          >
        </v-list-item>

        <v-list-group :value="true" prepend-icon="mdi-cash-multiple">
          <template v-slot:activator>
            <v-list-item-title>Payment</v-list-item-title>
          </template>

          <v-list-item v-for="([title], i) in admins" :key="i" link>
            <v-list-item-title class="list" v-text="title"></v-list-item-title>
          </v-list-item>
        </v-list-group>
        <v-list-item>
          <v-list-item-icon>
            <v-icon>mdi-autorenew</v-icon>
          </v-list-item-icon>

          <v-list-item-title
            ><router-link style="text-decoration: none; color: inherit" to="#"
              >Balance</router-link
            ></v-list-item-title
          >
        </v-list-item>
        <v-list-item>
          <v-list-item-icon>
            <v-icon>mdi-account-circle</v-icon>
          </v-list-item-icon>

          <v-list-item-title
            ><router-link style="text-decoration: none; color: inherit" to="#"
              >Consumers</router-link
            ></v-list-item-title
          >
        </v-list-item>
        <v-list-item>
          <v-list-item-icon>
            <v-icon>mdi-account-switch-outline</v-icon>
          </v-list-item-icon>

          <v-list-item-title
            ><router-link style="text-decoration: none; color: inherit" to="#"
              >Connected accounts</router-link
            ></v-list-item-title
          >
        </v-list-item>
        <v-list-item>
          <v-list-item-icon>
            <v-icon>mdi-package-variant-closed</v-icon>
          </v-list-item-icon>

          <v-list-item-title
            ><router-link style="text-decoration: none; color: inherit" to="#"
              >Products</router-link
            ></v-list-item-title
          >
        </v-list-item>
        <v-list-item>
          <v-list-item-icon>
            <v-icon>mdi-chart-bar</v-icon>
          </v-list-item-icon>

          <v-list-item-title
            ><router-link style="text-decoration: none; color: inherit" to="#"
              >Reports</router-link
            ></v-list-item-title
          >
        </v-list-item>
        <v-list-item class="dev">
          <v-list-item-icon>
            <v-icon>mdi-cash-multiple</v-icon>
          </v-list-item-icon>

          <v-list-item-title
            ><router-link style="text-decoration: none; color: inherit" to="#"
              >Developers</router-link
            ></v-list-item-title
          >
        </v-list-item>
        <v-list-item>
          <v-list-item-icon>
            <v-switch v-model="switch1" inset class="switch"></v-switch>
          </v-list-item-icon>

          <v-list-item-title class="mt-5">View test data</v-list-item-title>
        </v-list-item>
        <v-list-item>
          <v-list-item-icon>
            <v-icon>mdi-cog</v-icon>
          </v-list-item-icon>

          <v-list-item-title
            ><router-link style="text-decoration: none; color: inherit" to="#"
              >Settings</router-link
            ></v-list-item-title
          >
        </v-list-item>
      </v-list-group>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  name: "DrawerMenu",
  props: {
    value: {
      type: Boolean,
      // required: true,
      default: true,
      // clipped: false,
    },
  },
  data: () => ({
    admins: [
      ["Reviews", "#"],
      ["Disputes"],
      ["Top-ups"],
      ["Collected fees"],
      ["Transfers"],
      ["Payouts"],
      ["All transactions"],
    ],
  }),
};
</script>

<style scoped>
.store {
  font-weight: 500;
  font-size: 20px;
  line-height: 19px;
}
.btn {
  display: flex;
}
.switch {
  width: 5px;
  height: 24px;
}
.dev {
  margin-top: 2rem;
}
.list {
  margin-left: 4rem;
}
router-link {
  text-decoration: none;
}
</style>
