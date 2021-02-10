<template>
  <div>
    <ul>
      <li v-for="dish of dishes" v-bind:key="dish.id">
        {{ dish.name }} - {{ dish.description }} - {{ dish.price }}
        <button type="button" @click="onItemClicked(dish)">ADD</button>
      </li>
    </ul>
    {{ totalDishes }}
  </div>
</template>

<script>
import { dishes } from '../config/dishesMocked' 

export default {
  data() {
    return {
      dishes,
    }
  },
  computed: {
    totalDishes() {
      return this.dishes.lenght
    },
  },
  methods: {
    onItemClicked(dish) {
      this.$emit('itemClicked', dish)
    },
  },
}
</script>

<style></style>
