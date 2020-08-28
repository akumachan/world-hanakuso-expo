<template>
  <div id="app">
    <div class="hanakuso">
      {{ i18n.$t('hanakuso') }}
    </div>
    <div id="langs">
      <div class="lang" @click="changeLanguage('en')">en</div>
      <div class="lang" @click="changeLanguage('ja')">ja</div>
      <div class="lang" @click="changeLanguage('es')">es</div>
      <div class="lang" @click="changeLanguage('kr')">kr</div>
      <div class="lang" @click="changeLanguage('ru')">ru</div>
      <div class="lang" @click="changeLanguage('zh')">zh</div>
    </div>
  </div>
</template>

<script>
import { provideI18n, useI18n } from '@/i18nPlugin'

export default {
  name: 'App',
  setup() {
    provideI18n({
      locale: "en",
      messages: {
        en: { hanakuso: "Booger" },
        ja: { hanakuso: "鼻くそ" },
        es: { hanakuso: "Moco" },
        kr: { hanakuso: "코딱지" },
        ru: { hanakuso: "козявка" },
        zh: { hanakuso: "布格" },
      }
    });
    const i18n = useI18n();
    const changeLanguage = (lang) => {
      i18n.locale.value = lang;
    };

    return { i18n, changeLanguage };
  }
}
</script>

<style>
#app {
  display: flex;
  justify-content: center;
  flex-direction: column;
}
.hanakuso {
  color: darkslategray;
  font-size: 60px;
  text-align: center;
}
#langs {
  display: flex;
  justify-content: center;
  margin: 5px 0
}
.lang {
  margin: 0 3px;
  cursor: pointer;
}
</style>
