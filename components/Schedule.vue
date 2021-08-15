<template>
  <div class="card rounded shadow-sm">
    <div class="card-body">
      <div class="row">
        <div class="col-1 border-right border-black">
          <img :src="img" alt="" srcset="/icon.png" class="w-100">
        </div>
        <div class="col">
          <h6 class="p-0 m-0">{{title}} : {{type}}</h6>
          <p class="p-0 m-0">{{$moment(schedule).format("DD MMMM")}}</p>
        </div>
        <div class="col-1 d-flex align-items-center ">
          <elipsis />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    type: { type: String, default: "Materi" },
    title: { type: String, default: "Judul Jadwal" },
    schedule: { type: String, default: "2021-12-24" },
    img: String,
  },
};
</script>