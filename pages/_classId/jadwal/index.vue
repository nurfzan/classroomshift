<template>
  <div class="row">
    <div class="col-3">
      <div class="nav flex-column nav-pills" id="v-pills-tab" role="tablist" aria-orientation="vertical">
        <a class="nav-link d-flex justify-content-between" id="v-pills-home-tab" data-toggle="pill" href="#v-pills-home" role="tab" aria-controls="v-pills-home" aria-selected="true">Home
          <elipsis />
        </a>
      </div>
      <div class="text-center mt-5">
        <nuxt-link class="text-primary" :to="`/${$route.params.classId}/jadwal/add`">+ Jadwal</nuxt-link>
      </div>
    </div>
    <div class="col-9">
      <div class="tab-content" id="v-pills-tabContent">
        <div class="tab-pane fade show active" id="v-pills-home" role="tabpanel" aria-labelledby="v-pills-home-tab">
          <material-item />
        </div>
      </div>
      <div class="text-center mb-3">
        <button type="button" class="btn btn-default rounded-pill">+ Materi</button>
      </div>
    </div>
  </div>
</template>
<script>
export default {};
</script>