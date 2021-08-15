<template>
  <div class="row">
    <div class="col-md-3" v-for="i in 10" :key="i">
      <class-item :title="'mastery '+(i+1)" :desc="`description mastery ke ${i+1}
Lorem ipsum dolor, sit amet consectetur adipisicing elit. Doloribus distinctio mollitia iste, voluptatum, numquam debitis corporis voluptatibus, sint nulla natus doloremque culpa omnis id ex ea consequuntur consequatur molestias quod?
      `" />
    </div>
  </div>
</template>

<script>
export default {};
</script>
