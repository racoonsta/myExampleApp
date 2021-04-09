<template>
  <div class="example-item">
    <div class="example__logo">
    <URLGenerator
      v-bind:cardId="cardRecord.id">
      <img class="example__image"
      :src="cardRecord.sImage" alt="Image">
    </URLGenerator>
    </div>
    <div class="example__title">
      <span>{{ cardRecord.sWork }}</span>
    </div>
    <div class="example__descr">
      <ul>
        <li v-if="cardRecord.sTitle1">{{ cardRecord.sTitle1 }}</li>
        <li v-if="cardRecord.sTitle2">{{ cardRecord.sTitle2 }}</li>
        <li v-if="cardRecord.sTitle3">{{ cardRecord.sTitle3 }}</li>
      </ul>
    </div>
    <div class="example__footer">
      <a v-if=cardRecord.sGithubLink
        :href=cardRecord.sGithubLink>
        <img src="github.png" alt="">
      </a>
      <a v-else href="#">
        <img class="github__disabled" src="github.png" alt="">
      </a>
    </div>
  </div>
</template>

<script>
import URLGenerator from '@/components/URLGenerator.vue'
export default {
  name: 'CardComponent',
  props: {
    cardRecord: {
      required: true,
      type: Object
    }
  },
  components: {
    URLGenerator
  }
}
</script>

<style lang="scss">
  .example {
    &-item {
    position: relative;
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    flex-direction: column;
    margin-top: 30px;
    border: 1px solid gray;
    border-radius: 5px;
    width: 260px;
    min-height: 420px;
    }
    &__logo {
      opacity: 0.8;
    }
    &__logo:hover {
      opacity: 1;
      cursor: pointer;
    }
    &__title span {
      font-weight: 700;
      font-size: 18px;
    }
    &__descr {
      display: block;
      min-height: 80px;
    }
    &__descr ul {
      min-width: 180px;
    }
    &__descr li {
      text-align: left;
    }
    &__footer img {
      display: block;
      position: relative;
      width: 64px;
      height: 64px;
    }
    &__footer a {
      cursor: pointer;
    }
  }
  .github__disabled {
  opacity: 0.5;
  cursor: default;
  }
  @media (max-width: 786px) {
  .example__logo {
    opacity: 1;
    }
  }
</style>
