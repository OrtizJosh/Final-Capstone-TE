<template>
  <div class="tutorial">
    <div class="abstract">
      <h1 id="welcome">Welcome to Key Choices!</h1>
      <h2>
        Let us help simplify your meal times while keeping your dietary needs in
        mind.
      </h2>
    </div>

    <div class="steps">
      <h3 id="info"><br />How to Navigate our site:</h3>
<td class="stepList">
      <tr id="stepOne">
        <span name="first"> Step 1- </span>
        Once you are logged in click on the "All Recipes" tab and take time to browse
        our recipe inventory.
      </tr>
      <br />

      <tr name="stepTwo">
        <span name="second"> Step 3-</span>
        Choose your dietary restrictions by choosing the icon on the top. Watch
        the list morph to one that fits you.
      </tr>
      <br />
      <tr name="stepThree">
        <span name="third"> Step 4- </span>
        Check the recipes that excite you. Click "Add to your list" to store them
        in a personal recipe list.
      </tr>
      <br />
      <tr name="stepFour">
        <span name="fourth"> Step 5- </span>
        Click the "My Recipes" tab to view and select your stored recipes.
      </tr>
      <br />
      <tr name="stepFive">
        <span name="fifth"> Step 6- </span>
        After checking the recipes for this weeks' grind select the "Create
        Grocery List" button and we'll create a customized shopping list for you.
      </tr>
      <br />
      </td>
    </div>

    <div>
      <h4 class="answer">
        Here you can see one of our recipes! When you click the plate it will
        bring up the recipe details and instructions!
      </h4>
    </div>
    <div class="tutorialCard">
      <router-link
        class="tutorialLink"
        v-bind:to="{ name: 'error', params: { id: recipe.recipeID } }"
      >
        <div class="card">
          <img class="plate" src="../assests/plate.png" />
          <img class="recipe-image" v-bind:src="recipe.image" />
        </div>
        <h4 class="recipe-title">{{ recipe.name }}</h4>
      </router-link>
    </div>

  
    <div class= "navigation">
      <p> <br>
        When you are ready head
        <span>
          <router-link v-bind:to="{ name: 'register' }"
            >Here
          </router-link></span
        >
        sign up or if you have signed up head
        <span>
          <router-link v-bind:to="{ name: 'login' }">Here </router-link></span
        >
        to login!
      </p>
    </div>
  </div>
</template>

<script>
export default {
  computed: {
    recipe() {
      return this.$store.state.recipes.find((f) => f.recipeID === 1);
    },
  },
};
</script>


<style scoped>
.tutorial{
  color: white;  
  font-family: "Berkshire Swash", cursive; 
 
}
.tutorialLink{
  display: flex;
  flex-direction: column;
  align-items: center;
}

.tutorialCard {
  display: flex;
  flex-direction: column;
}
.card {
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  width: 100px;
  height: 100px;
}

.plate {
  position: absolute;
  width: 100px;
  height: 100px;
  z-index: -1;
}

.card:hover {
  border-style: solid;
  border-color: rgb(255, 255, 255, 0.5);
  border-width: 5px;
}

.recipe-image {
  border-radius: 50%;
  height: 50%;
  width: 50%;
  align-content: center;
}

.recipe-title {
  text-align: center;
  color: #ffffff;
  font-size: 0.9rem;
  font-family: "Kalam", cursive;
  text-shadow: -1px -1px 0 #000, 1px -1px 0 #000, -1px 1px 0 #000,
    1px 1px 0 #000;
}

#welcome {
  text-align: center;
}
.answer {
  text-align: center;
}
.abstract>h3, .abstract>h4{
  text-align: center;
}
#info {
  text-align: center;
}
.navigation {
  text-align: center;
  font-size: 1.5em;
}
a {
  color: yellow;
}

.steps{
  text-indent: 10px;
  font-family: "pencilPete";
  background-image: url("../assests/chalkboard.webp");

  background-repeat: no-repeat;
  background-size: 100%;
  opacity: .9;
  height: 350px;
  font-size: 1.25em;
  box-shadow: 0 0 8px 8px maroon inset;
  
 
}
.stepList{
  text-indent: 80px;
}
h2{
  text-align: center;
  margin-bottom: 80px;
}
h1{
  margin: 32.16px 0px;
  font-size: 48px;
}



</style>
