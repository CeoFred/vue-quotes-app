<template>
  <div class="row">
    <app-quote
      @click.native="deleteQuote(index)"
      v-for="(quote, index) in quotes"
      v-bind:key="quote"
      >
      <div>
        {{ quote }}
      </div>
      </app-quote
    >
  </div>
</template>

<script>
import Quote from "./Quote";

export default {
  props: ["quotes"],
  components: {
    appQuote: Quote
  },
  methods: {
    deleteQuote(index) {
      this.$emit("quoteDeleted", index);
    }
  }
};
</script>
