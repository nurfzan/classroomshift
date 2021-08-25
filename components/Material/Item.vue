<template>
  <nuxt-link :to="`/${$route.params.classId}/jadwal?materi=${id}`" class="card rounded shadow-sm text-decoration-none">
    <div class="card-body">
      <div class="row border-black border-bottom">
        <div class="col">
          <h6 class="p-0 m-0">{{title}} : {{type}}</h6>
          <p class="p-0 m-0">{{$moment(schedule).format("DD MMMM")}}</p>
        </div>
        <div class="col-1 d-flex align-items-center ">
          <i class="fas fa-ellipsis-v dropdown-toggle pointer" data-toggle="dropdown" style="font-size:1.4em"></i>
          <div class="dropdown-menu">
            <a class="dropdown-item" href="#">Sunting</a>
            <a class="dropdown-item" href="#">Hapus</a>
          </div>
        </div>
      </div>
      <div class="container mt-3">
        <a :href="file" target="_blank" rel="noopener noreferrer">
          <i class="fas fa-file-download" style="font-size:3em"></i>
        </a>
      </div>
    </div>
  </nuxt-link>
</template>
<script>
export default {
  props: {
    id: { type: String, default: "materi-id" },
    type: { type: String, default: "Materi" },
    title: { type: String, default: "Judul Jadwal" },
    schedule: { type: String, default: "2021-12-24" },
    file: String,
    img: String,
  },
};
</script>