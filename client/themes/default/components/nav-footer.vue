<template lang="pug">
  v-footer.justify-center(:color='bgColor', inset)
    .caption.grey--text.text--darken-1
      span
        b UAS@UCLA {{ currentYear }}.{{" "}}
        span {{ "A division of AIAA at UCLA. " }}
        a(href='https://github.com/uas-at-ucla/website' style='color: inherit; text-decoration: underline;') Source code
</template>

<script>
import { get } from 'vuex-pathify'

export default {
  props: {
    color: {
      type: String,
      default: 'grey lighten-3'
    },
    darkColor: {
      type: String,
      default: 'grey darken-3'
    }
  },
  data() {
    return {
      currentYear: (new Date()).getFullYear()
    }
  },
  computed: {
    company: get('site/company'),
    contentLicense: get('site/contentLicense'),
    bgColor() {
      if (!this.$vuetify.theme.dark) {
        return this.color
      } else {
        return this.darkColor
      }
    }
  }
}
</script>

<style lang="scss">
  .v-footer {
    a {
      text-decoration: none;
    }

    &.altbg {
      background: mc('theme', 'primary');

      span {
        color: mc('blue', '300');
      }

      a {
        color: mc('blue', '200');
      }
    }
  }
</style>
