<template>
<div id="eachDish">
    <h1>{{ dish.dish }}</h1>
    <h2>{{ dish.description }}</h2>
    <p>{{ dish.price }}</p>
</div>

</template>

<script>
export default {
    data() {
        return{
            dish,
        }
    }

}
</script>

<style>

</style>