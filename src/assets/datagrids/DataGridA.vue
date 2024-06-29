<template>
  <div>
    <localization :language="localizationLanguage">
      <intl :locale="locale">
        <Grid @localizationLanguageChange="onLocalizationLanguageChange"></Grid>
      </intl>
    </localization>
  </div>
</template>

<script setup lang="ts">
import Grid from "./Grid.vue";
import {
  load,
  LocalizationProvider,
  IntlProvider,
  loadMessages,
} from "@progress/kendo-vue-intl";
import {ref, computed} from 'vue';
import { enComponentMessages, enCustomMessages } from "./en-US";
import { esComponentMessages, esCustomMessages } from "./es";
import { frComponentMessages, frCustomMessages } from "./fr";

import likelySubtags from "cldr-core/supplemental/likelySubtags.json";
import currencyData from "cldr-core/supplemental/currencyData.json";
import weekData from "cldr-core/supplemental/weekData.json";

import numbers from "cldr-numbers-full/main/es/numbers.json";
import caGregorian from "cldr-dates-full/main/es/ca-gregorian.json";
import dateFields from "cldr-dates-full/main/es/dateFields.json";
import timeZoneNames from "cldr-dates-full/main/es/timeZoneNames.json";
import esNumbers from "cldr-numbers-full/main/es/numbers.json";
import esCurrencies from "cldr-numbers-full/main/es/currencies.json";

import frNumbers from "cldr-numbers-full/main/fr/numbers.json";
import frCaGregorian from "cldr-dates-full/main/fr/ca-gregorian.json";
import frDateFields from "cldr-dates-full/main/fr/dateFields.json";
import frTimeZoneNames from "cldr-dates-full/main/fr/timeZoneNames.json";
import frCurrencies from "cldr-numbers-full/main/fr/currencies.json";

load(
  likelySubtags,
  currencyData,
  weekData,
  numbers,
  caGregorian,
  dateFields,
  timeZoneNames,
  esNumbers,
  esCurrencies,
  frNumbers,
  frCaGregorian,
  frDateFields,
  frTimeZoneNames,
  frCurrencies
)

loadMessages(enCustomMessages, "English");
loadMessages(enComponentMessages, "English");
loadMessages(esCustomMessages, "Spanish");
loadMessages(esComponentMessages, "Spanish");
loadMessages(frCustomMessages, "French");
loadMessages(frComponentMessages, "French");

const localizationLanguage = ref("English");

const locales = [
  {
    language: "English",
    locale: "en",
  },
  {
    language: "French",
    locale: "fr",
  },
  {
    language: "Spanish",
    locale: "es",
  },
]

const locale = computed(() => {
  if (localizationLanguage.value === "Spanish") {
    return "es"
  }

  if (localizationLanguage.value === "French") {
    return "fr"
  }

  return "en"
})

const onLocalizationLanguageChange = (language) => {
  localizationLanguage.value = language;
}

</script>

<style>
</style>