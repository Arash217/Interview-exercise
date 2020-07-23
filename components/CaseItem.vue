<template>
  <div>
    <div class="image__container">
      <img class="image--max-width-1200 image--padding-bottom" :src="teaserImage">
    </div>
    <div class="content--center-align">
      <p class="content__text content__text--big">{{ teaserTitle }}</p>
      <p class="content__text">
        {{ loremIpsum }}
      </p>
      <p class="content__text">
        {{ loremIpsum }}
      </p>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      teaserTitle: {
        type: String,
        default: ''
      },
      teaserImage: {
        type: String,
        default: ''
      }
    },

    data() {
      return {
        loremIpsum: `Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore
        magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
        consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
        pariatur.
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum`
      }
    },
  }
</script>
