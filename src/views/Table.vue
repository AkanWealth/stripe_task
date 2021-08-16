<template>
  <div>
    <v-data-table
      :headers="headers"
      v-model="selected"
      :items="desserts"
      :single-select="singleSelect"
      item-key="name"
      show-select
      class="elevation-1"
      :custom-filter="filterOnlyCapsText"
    >
      <template v-slot:top>
        <v-toolbar flat>
          <v-toolbar-title
            style="
              font-weight: bold;
              font-size: 28px;
              line-height: 33px;
              color: #1a1f36;
            "
            >Payments</v-toolbar-title
          >
          <v-spacer></v-spacer>
          <v-btn class="ma-2" grey--text color="white"
            ><v-icon dark> mdi-filter</v-icon> Filter</v-btn
          >
          <v-btn class="ma-2" grey--text color="white"
            ><v-icon dark> mdi-arrow-top-right</v-icon>Export</v-btn
          >
          <v-btn class="ma-2 white--text" color="primary"
            ><v-icon dark> mdi-plus</v-icon>Create payment</v-btn
          >
        </v-toolbar>
        <v-tabs align-with-title>
          <v-tab>All</v-tab>
          <v-tab>Succeeded</v-tab>
          <v-tab>Refunded</v-tab>
          <v-tab>Uncaptured</v-tab>
        </v-tabs>
        <hr />
      </template>
      <template>
        <tr>
          <td></td>
          <td>
            <v-text-field
              v-model="amount"
              type="number"
              label="Less than"
            ></v-text-field>
          </td>
          <td colspan="4"></td>
        </tr>
      </template>
    </v-data-table>
  </div>
</template>

<script>
export default {
  data: () => ({
    singleSelect: false,
    selected: [],
    desserts: [
      {
        amount: "US$352.22",
        desc: "fe3d8216-58f9-4dc1-aaef-2f19463b5258",
        success: "Succeeded",
        customer: "hefovo87@ereyemind...",
        date: "7 Jul, 14:04",
        protein: 4.0,
        iron: "1%",
      },
      {
        amount: "US$152.22",
        desc: "fe3d8216-58f9-4dc1-aaef-2f19463b5258",
        success: "Succeeded",
        customer: "hello@gmail.com",
        date: "7 Jul, 14:04",
        protein: 4.3,
        iron: "1%",
      },
      {
        amount: "US$322.23",
        desc: "fe3d8216-58f9-4dc1-aaef-2f19463b5258",
        success: "Succeeded",
        customer: "hello@gmail.com",
        date: "7 Jul, 14:04",
        protein: 6.0,
        iron: "7%",
      },
      {
        amount: "US$234.22",
        desc: "fe3d8216-58f9-4dc1-aaef-2f19463b5258",
        success: "Succeeded",
        customer: "hefovo87@ereyemind...",
        date: "7 Jul, 14:04",
        protein: 4.3,
        iron: "8%",
      },
      {
        amount: "US$352.22",
        desc: "fe3d8216-58f9-4dc1-aaef-2f19463b5258",
        success: "Succeeded",
        customer: "hefovo87@ereyemind...",
        date: "7 Jul, 14:04",
        protein: 3.9,
        iron: "16%",
      },
      {
        amount: "US$112.22",
        desc: "fe3d8216-58f9-4dc1-aaef-2f19463b5258",
        success: "Succeeded",
        customer: "hefovo87@ereyemind...",
        date: "7 Jul, 14:04",
        protein: 0.0,
        iron: "0%",
      },
      {
        amount: "US$352.24",
        desc: "fe3d8216-58f9-4dc1-aaef-2f19463b5258",
        success: "Succeeded",
        customer: "hefovo87@ereyemind...",
        date: "7 Jul, 14:04",
        protein: 0,
        iron: "2%",
      },
      {
        amount: "US$332.24",
        desc: "fe3d8216-58f9-4dc1-aaef-2f19463b5258",
        success: "Succeeded",
        customer: "info@gmail.com",
        date: "7 Jul, 14:04",
        protein: 6.5,
        iron: "45%",
      },
      {
        amount: "US$322.22",
        desc: "fe3d8216-58f9-4dc1-aaef-2f19463b5258",
        success: "Succeeded",
        customer: "info@gmail.com",
        date: "7 Jul, 14:04",
        protein: 4.9,
        iron: "22%",
      },
      {
        amount: "US$434.22",
        desc: "fe3d8216-58f9-4dc1-aaef-2f19463b5258",
        success: "Succeeded",
        customer: "hefovo87@ereyemind...",
        date: "7 Jul, 14:04",
        menu: "...",
        iron: "6%",
      },
    ],
  }),
  computed: {
    headers() {
      return [
        {
          text: "AMOUNT",
          align: "start",
          sortable: false,
          value: "amount",
        },
        { text: "", value: "success" },
        {
          text: "DESCRIPTION",
          value: "desc",
        },
        { text: "" },
        { text: "CUSTOMER", value: "customer" },
        { text: "DATE", value: "date" },
        { text: "", value: "menu" },
      ];
    },
  },
  methods: {
    getColor(success) {
      if (success !== success) return "red";
      else if (success === success) return "orange";
      else return "green";
    },
  },
};
</script>
