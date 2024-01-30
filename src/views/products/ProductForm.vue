<template>
  <form @submit.prevent="submit">
     <div class="mb-3">
       <v-text-field label="Title" v-model="title"/>
     </div>
     <div class="mb-3">
       <v-textarea label="Description" v-model="description" />
     </div>
     <div class="mb-3">
       <v-text-field label="Image" v-model="image"/>
     </div>
     <div class="mb-3">
       <v-text-field label="Price" type="number" min="0" v-model="price"/>
     </div>

    <v-btn color="primary" type="submit">Save</v-btn>

  </form>
</template>

<script>
import axios from "axios";

export default {
  name: "ProductForm",

  data() {
    return {
      title: '',
      description: '',
      image: '',
      price: ''
    }
  },

  methods: {
    async submit() {
      await axios.post('products', {
        title: this.title,
        description: this.description,
        image: this.image,
        price: this.price
      });

      await this.$router.push('/products');
    }
  }
}
</script>

<style scoped>

</style>