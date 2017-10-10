<template>
  <div class="row">
    <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
      <form>
        <div class="form-group">
          <label for="quote">Quote</label>
          <textarea class="form-control" name="quote" rows="3" v-model="quote"></textarea>
        </div>
        <button type="button" class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
      </form>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        quote: '',
      };
    },
    methods: {
      createNew() {
        this.$emit('quoteAdded', this.quote);
        this.quote = '';
      },
    },
  };
</script>

<style scoped>
  textarea {
    resize: none;
  }
</style>
