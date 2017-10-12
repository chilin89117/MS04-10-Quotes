<template>
  <div class="container">
    <appHeader :quoteCount="quotes.length" :maxQuotes="maxQuotes"></appHeader>
    <appNewQuote @quoteAdded="addQuote"></appNewQuote>
    <hr>
    <appQuoteGrid :quotes="quotes"
                  @quoteDeleted="deleteQuote"></appQuoteGrid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          Info: Click on a quote to delete it.
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import QuoteGrid from './components/QuoteGrid.vue'
  import NewQuote from './components/NewQuote.vue'
  import Header from './components/Header.vue'

  export default {
    data() {
      return {
        maxQuotes: 12,
        quotes: [],
      };
    },
    components: {
      appQuoteGrid: QuoteGrid,
      appNewQuote: NewQuote,
      appHeader: Header,
    },
    methods: {
      addQuote(quote) {
        if(this.quotes.length >= this.maxQuotes) {
          return alert('Maximum number of quotes reached. Delete some first.');
        }
        this.quotes.unshift(quote);
      },
      deleteQuote(index) {
        this.quotes.splice(index, 1);
      },
    },
  };
</script>
