<template>
  <div class="row">
    <div class="col-sm-12">
      <h3>Quotes Added</h3>

      <div class="progress">
        <div class="progress-bar" role="progressbar" :aria-valuenow="pct"
             aria-valuemin="0" aria-valuemax="100" :style="{width: pct + '%'}">
          <span>{{quoteCount}} / {{maxQuotes}}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: [
      'quoteCount',
      'maxQuotes',
    ],
    computed: {
      pct() {
        return (this.quoteCount / this.maxQuotes) * 100;
      },
    },
  };
</script>
