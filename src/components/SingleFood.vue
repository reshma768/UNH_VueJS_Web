<!-- SingleFood.vue -->
<template>
  <div :class="{ 'expired': isExpired }">
    <h2>{{ food.title }}</h2>
    <p>Protein: {{ food['Protein(grams)'] }} grams</p>
    <p>Calories: {{ food.Calories }}</p>
    <p>Expiration Date: {{ food['Expiration Date'] }}</p>
  </div>
</template>

<script>
export default {
  name: 'SingleFood',
  props: {
    food: Object,
  },
  computed: {
    isExpired() {
      const expirationDate = new Date(this.food['Expiration Date']);
      const currentDate = new Date();
      return expirationDate < currentDate;
    },
  },
};
</script>

<style scoped>
.expired {
  background-color: #FF0000;
  color: #272424; 
  
}

h4{
    margin: 2px;
}

div{
    background-color: #88eb88;
    color: black;
    padding: 1em;
    text-align: center;
    width: 80%;
    margin: auto;
    
    

}
</style>
