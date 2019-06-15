<template lang="pug">
  v-footer.justify-center(:color='bgColor', inset)
    .caption.grey--text.text--darken-1
      span(v-if='company && company.length > 0', style="font-weight: bold") {{ $t('common:footer.copyright', { company: company, year: currentYear, interpolation: { escapeValue: false } }) }}
      span(style="margin-left: 5px") {{ $t('common:footer.division') }}
      span(style="margin-left: 5px") {{ $t('common:footer.lastEdited', { person: authorName, time: updatedAtFormatted, interpolation: { escapeValue: false } }) }}
</template>

<script>
import { get } from 'vuex-pathify'
var moment = require('moment');

export default {
  props: {
    color: {
      type: String,
      default: 'grey lighten-3'
    },
    darkColor: {
      type: String,
      default: 'grey darken-3'
    },
    updatedAt: {
      type: String,
      default: ''
    },
    authorName: {
      type: String,
      default: 'Unknown'
    }
  },
  data() {
    return {
      currentYear: (new Date()).getFullYear()
    }
  },
  computed: {
    company: get('site/company'),
    darkMode: get('site/dark'),
    authorName: get('page/authorName'),
    updatedAt: get('page/updatedAt'),
    updatedAtFormatted() {
      return moment(this.updatedAt).calendar().toLowerCase()
    },
    bgColor() {
      if (!this.darkMode) {
        return this.color
      } else {
        return this.darkColor
      }
    }
  },
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
