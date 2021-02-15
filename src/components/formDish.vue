<template>
  <div class="formDish">
    <div class="eachDish">
      <form id="dishes" action="" method="post">
        <input v-model="dish" placeholder="Add Dish Name" />
        <input v-model="description" placeholder="Add Dish Description" />
        <input v-model="price" placeholder="price" />
        <button @click="addDish(dish)">ADD NEW DISH</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dishesList,
      formDish,
    }
  },
}

</script>
