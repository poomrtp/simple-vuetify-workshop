<template>
  <div class="my-12">
    <v-row>
      <v-col cols="3" v-for="(item, index) in productItems" :key="index">
        <v-card class="mx-auto" max-width="374">
          <v-img height="250" src="../assets/logo.png"></v-img>
          <v-card-title>{{ item.name }}</v-card-title>
          <v-card-text>
            <div>
              {{ item.description }}
            </div>
          </v-card-text>
          <v-divider class="mx-4"></v-divider>
          <v-card-text>
            <div>Price : {{ item.price }}</div>
          </v-card-text>
          <v-card-actions class="d-flex justify-end">
            <v-btn color="deep-purple lighten-2" text>Add to cart</v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>
<script>
export default {
  name: 'ProductList',
  components: {},
  data() {
    return {
      productItems: [
        { name: 'vuejs1', description: 'Basic vuejs with workshop', price: 120 },
        { name: 'vuejs1', description: 'Basic vuejs with workshop', price: 120 },
        { name: 'vuejs1', description: 'Basic vuejs with workshop', price: 120 },
        { name: 'vuejs1', description: 'Basic vuejs with workshop', price: 120 },
        { name: 'vuejs1', description: 'Basic vuejs with workshop', price: 120 }
      ]
    }
  }
}
</script>
