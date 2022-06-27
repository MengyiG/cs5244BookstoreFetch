<template>
  <nav class="category-nav">
    <ul class="category-buttons">
      <template v-for="category in categories">
        <li
          v-if="category.name === $route.params.name"
          :key="category.categoryId"
          class="button selected-category-button"
        >
          {{ category.name }}
        </li>
        <li
          v-else
          :key="category.categoryId"
          class="button unselected-category-button"
        >
          <router-link :to="'../category/' + category.name"
            >{{ category.name }}
          </router-link>
        </li></template
      >

      <!--      codes before binding
      <router-link
        to="../category/fantasy"
        tag="li"
        class="button unselected-category-button"
      >
        Fantasy
      </router-link>
      -->
    </ul>
  </nav>
</template>

<script>
export default {
  name: "CategoryNav",
  data: function () {
    return {
      //create a categories array to hold the fetched categories
      categories: [],
    };
  },
  created() {
    this.fetchCategoties();
  },
  methods: {
    fetchCategoties() {
      //this refers to the component
      const vm = this;
      const baseUrl = "http://localhost:8080/MengyiBookstoreFetch/api";
      return (
        fetch(baseUrl + "/categories")
          .then((response) => response.json())
          //  passing in the parsed JSON
          .then((data) => {
            console.log("Data: ", data);
            //if we use this instead of this
            //we refer to the object that the function is run on
            //but we need to refer to the component
            //assign it to the categories component
            vm.categories = data;
          })
          .catch((reason) => {
            console.log("Error: " + reason);
          })
      );
    },
  },
};
</script>

<style scoped>
.category-nav {
  height: 100%;
  background-color: var(--neutral-color);
  display: block;
  padding-top: 5%;
  flex-shrink: 0;
  min-width: 120pt;
  min-height: 320pt;
}

.category-buttons {
  display: flex;
  flex-direction: column;
  text-align: center;
  background-color: var(--neutral-color);
  line-height: 2em;
}

.button.selected-category-button {
  background-color: var(--primary-color);
  font-weight: bold;
}

.button.unselected-category-button,
.button.unselected-category-button:visited {
  background-color: var(--neutral-color);
}

.button.unselected-category-button:hover,
.button.unselected-category-button:active {
  font-weight: bold;
  background-color: var(--primary-color);
}

li a {
  color: var(--default-text-color);
  text-decoration: none;
}
</style>
