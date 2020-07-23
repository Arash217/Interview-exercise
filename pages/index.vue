<template>
  <main v-if="!$apollo.loading">
    <div class="content__background"></div>
    <div class="content">
      <header class="content__header content__header--yellow">
        <div class="content__header-text">
          <h1 class="content__header-text-title">Cases</h1>
          <p class="content__header-text-subtitle">Wij helpen je vooruit op het web</p>
        </div>
      </header>
      <div class="content__list-container">
        <Cases :all-case-items="allCaseItems" v-if="allCaseItems.length > 0"/>
        <div class="panel panel--padding-4 panel--white" v-else>
          <span class="panel__text">
            Geen cases...
          </span>
        </div>
      </div>
    </div>
  </main>
  <div class="content--center-align" v-else>
    <loading/>
  </div>
</template>

<script>
  import allCaseItems from '~/apollo/queries/allCaseItems'
  import Cases from '~/components/Cases';
  import Loading from '~/components/Loading';

  export default {
    components: {
      Cases,
      Loading
    },

    data() {
      return {
        allCaseItems: []
      }
    },

    apollo: {
      allCaseItems: {
        prefetch: true,
        query: allCaseItems
      }
    },
  }
</script>
