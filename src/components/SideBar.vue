<template>
  <v-navigation-drawer
  app
  color="#000000"
  mini-variant
  mini-variant-width="110"
  >
    <v-avatar class="d-block text-center mx-auto mt-4 mb-10" size="80">
      <v-btn class="ma-2" outlined large fab color="white">
        <v-icon x-large>mdi-basket</v-icon>
      </v-btn>
    </v-avatar>
    <v-card flat color="#151515" class="rounded-xl mx-4 py-10">
      <v-list flat dark>
        <v-list-item-group v-model="selectItem">
          <v-list-item
            v-for="(item, i) in items"
            :key="i"
            active-class="border"
            v-slot="{ active }"
            :ripple="false"
          >
            <v-list-item-content>
              <v-icon :color="active ? 'white' : 'grey-lighten-1'">
                {{ item.icon }}
              </v-icon>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-card>
    <div
      style="
        position: absolute;
        bottom: 20px;
        marign-left: auto;
        marign-right: auto;
        left: 0;
        right: 0;
        text-align: center;
      "
      >
      <v-avatar size="40">
        <v-img src="../assets/photo1.png" class="image"></v-img>
      </v-avatar>
    </div>
  </v-navigation-drawer>
</template>

<script>
export default {
  data: () => ({
    selectedItem: 0,

    items: [
      { icon: "mdi-home-outline" },
      { icon: "mdi-cart-outline" },
      { icon: "mdi-store-outline" },
      { icon: "mdi-calendar-check-outline" },
      { icon: "mdi-apps" },
    ],
  }),
  props: ["drawer"],
  watch: {
    drawer(value) {
      return value;
    },
  },
};
</script>

<style>
.border {
  margin: 0px 8px;
  background: #6f0dff;
  border-radius: 15px;
  text-decoration: none;
  width: 60px;
  height: 60px;
}

.v-list-item-group .v-list-item--active {
  color: #fff !important;
}

.v-list-item__content {
  padding: 20px 0 !important;
}

.image {
  border: 1px solid white;
}
</style>
