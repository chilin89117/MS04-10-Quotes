<template>
  <div class="col-sm-6 col-md-4 col-lg-3">
    <div class="panel panel-default">
      <div class="panel-body quote">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
</script>

<style scoped>
  .panel-body {
    font-family: 'Arizonia', cursive;
    font-size: 2em;
    color: #666;
    box-shadow: 3px 3px 7px #777;
  }

  .quote {
    cursor: pointer;
    background-color: lightyellow;
  }

  .quote:hover {
    background-color: lightgreen;
  }
</style>
