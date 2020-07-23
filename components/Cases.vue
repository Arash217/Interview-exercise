<template>
  <ul class="list list--white list--max-width-1200">
    <nuxt-link
      v-for="caseItem in allCaseItems"
      :key="caseItem.id"
      :to="`cases/${caseItem.id}`"
      class="list__item-link list__item-card"
    >
      <li class="list__item">
        <article>
          <h3 class="list__item-title">{{ caseItem.title }}</h3>
          <div>
            <img class="list__item-image" :src="caseItem.heroIllustration.url" :alt="caseItem.title">
            <p class="list__item-description">{{ caseItem.subtitle }}</p>
          </div>
        </article>
      </li>
    </nuxt-link>
  </ul>
</template>

<script>
  export default {
    props: {
      allCaseItems: {
        type: Array,
        default: []
      }
    }
  }
</script>
