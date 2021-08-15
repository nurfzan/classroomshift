<template>
  <div>
    <div class="jumbotron">
      <h1 class="display-4">Hello, world!</h1>
      <p class="lead">This is a simple hero unit, a simple jumbotron-style component for calling extra attention to featured content or information.</p>
    </div>
    <div class="row">
      <div class="col-md-3">

      </div>
      <div class="col-md-9">
        <schedule v-for="i in 40" :key="i"/>
      </div>
    </div>
  </div>
</template>
<script>
export default {};
</script>