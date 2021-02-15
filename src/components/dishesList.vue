<template>
  <table>
    <tr>
      <th>Nombre</th>
      <th>Descripcion</th>
      <th>Precio</th>
    </tr>
  <tr v-for="dish of dishes" v-bind:key="dish.id">
    <td>{{ dish.dish }}</td>
    <td>{{ dish.description }}</td>
    <td>{{ dish.price }}</td>
    <td>
      <button @click="editDish(dish)">EDIT</button>
      <button @click="deleteDish(dish.id)">DELETE</button>
    </td>
  </tr>
  </table>
</template>

<script>
import  axios  from 'axios'

import { dishes } from '../config/dishesMocked'

export default {
  data() {
    return {
      dishes,
      dishesList,
    }
  },
  created() {
    this.fetchDishes()
  },
  computed: {
    totalDishes() {
      return this.dishes.lenght
    },
  },
  methods: {
    addDish(dish) {
      axios.post('http://127.0.0.1:8000/api/dishes').then((response)=>{this.fetchDishes()
      this.$emit('itemClicked', dish)
      }
      )
    },
    fetchDishes() {
      axios.get('http://127.0.0.1:8000/api/dishes')
      .then((response) => { 
        this.dishes = response.data 
        console.log(this.dishes)}
        )
      },
    deleteDish(id){
      axios.delete(`http://127.0.0.1:8000/api/dishes/${id}`).then((response)=>{
        this.fetchDishes()
        console.log(response)}
      )
    },
    editDish(id){
      axios.put(`http://127.0.0.1:8000/api/dishes/${id}`).then((response)=>{
        this.dish = response.data
        this.fetchDishes()
        console.log(response)}
      )
    },
  }
}
</script>

<style></style>
