<template>
  <nav class="category-nav">
    <ul class="category-buttons">
      <li class="button selected-category-button">Classics</li>
      <router-link
        to="../category/fantasy"
        tag="li"
        class="button unselected-category-button"
      >
        Fantasy
      </router-link>
      <router-link
        to="../category/wellness"
        tag="li"
        class="button unselected-category-button"
      >
        Wellness
      </router-link>
      <router-link
        to="../category/comedy"
        tag="li"
        class="button unselected-category-button"
      >
        Comedy
      </router-link>
      <router-link
        to="../category/romance"
        tag="li"
        class="button unselected-category-button"
      >
        Romance
      </router-link>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "CategoryNav",
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
}

.button.unselected-category-button,
.button.unselected-category-button:visited {
  background-color: var(--neutral-color);
}

.button.unselected-category-button:hover,
.button.unselected-category-button:active {
  font-weight: 900;
  background-color: var(--primary-color);
}
</style>
