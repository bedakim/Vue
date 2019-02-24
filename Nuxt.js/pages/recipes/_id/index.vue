<template>
  <section class="single-recipe">
    <h1>{{recipe.title}}</h1>
    <div>
      <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
    </div>
    <p>{{recipe.descriptionText}}</p>
  </section>
</template>
<script>
import Recipe from "@/components/Recipe";
import { Promise, resolve, reject } from "q";
export default {
  components: {
    Recipe
  },
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: "1",
              title: "piaaz",
              previewText: "awesome",
              descriptionText: "this is really good meal ",
              thumbnail:
                "https://ichef.bbci.co.uk/food/ic/food_16x9_832/recipes/one_pot_chorizo_and_15611_16x9.jpg"
            },
            {
              id: "2",
              title: "taco",
              previewText: "ukk",
              descriptionText: "this is really good meal ",
              thumbnail:
                "https://food.fnr.sndimg.com/content/dam/images/food/fullset/2018/6/0/FN_snapchat_coachella_wingman%20.jpeg.rend.hgtvcom.616.462.suffix/1523633513292.jpeg"
            }
          ].find(el => el.id === context.params.id)
        });
      }, 1500);
    });
  }
};
</script>

<style>
.single-recipe {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 30px;
}
.recipe-image {
  width: 100%;
}
</style>
