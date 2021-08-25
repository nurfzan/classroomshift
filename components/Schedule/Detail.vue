<template>
  <div>
    <h5><i class="fas fa-arrow-left mr-3 pointer" @click="$router.go(-1)"></i> Kelas lalalal</h5>
    <hr>
    <div class="container">
      <form @submit.prevent="submit">
        <input-text :val="payload.title" @get="(val)=>payload.title=val" name="Nama Jadwal" placeholder="Sesi 1" />
        <input-text :val="payload.start" @get="(val)=>payload.start=val" name="Waktu Mulai" type="datetime-local" placeholder="Sesi 1" />
        <input-text :val="payload.end" @get="(val)=>payload.end=val" name="Waktu Selesai" type="datetime-local" placeholder="Sesi 1" />
        <div class="text-right mt-5">
          <button class="btn btn-secondary mr-3" @click="$router.go(-1)" type="button">Batal</button>
          <button class="btn btn-primary" type="submit">Simpan</button>
        </div>
      </form>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      payload: { title: "", start: "", end: "" },
    };
  },
  methods: {
    submit() {
      alert(JSON.stringify(this.payload));
    },
  },
};
</script>