<!-- App.vue -->
<template>
  <div>
    <MyHeader foodName="Food Nutrition Tracker" foodNames="(Almond, Spinach, Salmon, Chicken Breast, Banana)" />
    <FoodBox :foods="foods" />
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue';
import FoodBox from './components/FoodBox.vue';

export default {
  name: 'App',
  components: {
    MyHeader,
    FoodBox,
  },
  data() {
    return {
      foods: [],
    };
  },
  methods: {
    async fetchFoods() {
      try {
        const response = await fetch('http://localhost:8112/Food');
        const data = await response.json();
        return data; // Return the data
      } catch (error) {
        console.error('Error fetching foods:', error);
        return []; // Return an empty array in case of an error
      }
    },
  },
  async created() {
    this.foods = await this.fetchFoods();
  },
};
</script>

<style>


@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
}
.container {
  max-width: 400px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 0.3em solid black;
  padding: 30px;
  border-radius: 5px;
}

div{
  margin-bottom: 0.5em;

}


</style>
