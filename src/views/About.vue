<i18n>
  {
  "en": {
  "hello": "hello world!"
  },
  "ja": {
  "hello": "こんにちは、世界！"
  }
  }
</i18n>

<template>
  <div class="about">
    <select v-model="locale">
      <option>en</option>
      <option>ja</option>
    </select>
    <p>message: {{ $t('hello') }}</p>
  </div>
</template>

<script>
  export default {
    data() {
      this.$i18n.locale = 'en'
      return { locale: 'en' }
    },
    methods: {
      toggleLocale() {
        console.log(this.lang)
        switch (this.lang) {
          case 'en':
            this.lang = 'ja'
            break
          case 'ja':
            this.lang = 'en'
            break
        }
      }
    },
    watch: {
      locale (val) {
        this.$i18n.locale = val
      }
    }
  }
</script>