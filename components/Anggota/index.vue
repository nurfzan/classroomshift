<template>
  <div class="card rounded">
    <img :src="img" class="card-img-top" srcset="https://cdn.idntimes.com/content-images/community/2021/01/119123141-407810150181509-1422355583125837259-n-b4afd07a06fc90dbdda827d84050f22b-e8365f86141239468aae567dbdc9d734_600x400.jpg" alt="...">
    <div class="row px-3">
      <div class="col">
        <h5 class="p-0 pt-2 m-0">{{name}}</h5>
        <p class="">{{role}}</p>
      </div>
      <div class="col-2 d-flex align-items-center">
        <elipsis />
      </div>
    </div>
  </div>
</template>
<script>
import Elipsis from "../Elipsis.vue";
export default {
  components: { Elipsis },
  props: {
    img: String,
    name: { type: String, default: "Nama" },
    role: { type: String, default: "student" },
  },
};
</script>