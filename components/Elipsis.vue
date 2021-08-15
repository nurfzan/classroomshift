<template>
  <div>
    <i class="fas fa-ellipsis-v dropdown-toggle pointer" data-toggle="dropdown" :style="`font-size:1em`"></i>
    <div class="dropdown-menu">
      <nuxt-link class="dropdown-item" :to="`/${$route.params.classId}/jadwal/${id}`">Sunting</nuxt-link>
      <a class="dropdown-item" @click="canDelete" href="#">Hapus</a>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    id: { type: String, default: "10bfd23-" },
    title: { type: String, default: "Judul Jadwal" },
  },
  methods: {
    async canDelete() {
      const { value } = await this.$swal({
        icon: "question",
        title: `Menghapus data jadwal ${this.title}`,
        text: `jadwal yang sudah dihapus tidak bisa dikembalikan lagi`,
        showCancelButton: true,
      });
      if (value) this.deleteSchedule();
    },
    async deleteSchedule() {
      this.$swal({
        icon: "success",
        title: `Oke...`,
        text: `Jadwal ${this.title} berhasil dihapus`,
      });
    },
  },
};
</script>