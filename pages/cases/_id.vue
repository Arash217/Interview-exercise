<template>
  <main class="content" v-if="!$apollo.loading">
    <div class="content__container">
      <header class="content__header">
        <nav class="nav">
          <nuxt-link to="/">
            <svg class="nav__svg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 306 306" preserveAspectRatio="none">
              <path d="M247.35 35.7L211.65 0l-153 153 153 153 35.7-35.7L130.05 153z"></path>
            </svg>
          </nuxt-link>
        </nav>
        <div class="content__header-text">
          <h1 class="content__header-text-title">{{ caseItem.title || '' }}</h1>
          <p class="content__header-text-subtitle">Case study</p>
        </div>
      </header>
      <article>
        <case-item
          v-if="caseItem.caseTeaser"
          :teaser-image="caseItem.caseTeaser.image.url"
          :teaser-title="caseItem.caseTeaser.title"
        />
      </article>
    </div>
  </main>
  <div class="content--center-align" v-else>
    <loading/>
  </div>
</template>

<script>
  import caseItem from '~/apollo/queries/caseItem'
  import CaseItem from '~/components/CaseItem';
  import Loading from '~/components/Loading';

  export default {
    components: {
      CaseItem,
      Loading
    },

    data() {
      return {
        caseItem: {}
      }
    },

    apollo: {
      caseItem: {
        prefetch: ({route}) => ({id: route.params.id}),
        query: caseItem,
        variables() {
          return {id: Number(this.$route.params.id)}
        }
      }
    },
  }
</script>
