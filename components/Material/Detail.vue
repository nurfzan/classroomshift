<template>
  <div>
    <h5><i class="fas fa-arrow-left mr-3 pointer" @click="$router.go(-1)"></i> Sesi 1</h5>
    <hr>
    <div class="container">
      <form @submit.prevent="submit">
        <input-text :val="payload.title" @get="(val)=>payload.title=val" name="Materi" placeholder="Materi 1" />
        <input-options :val="payload.type" @get="(val)=>payload.type=val" name="Tipe" :options="list" />
        <input-file :val="payload.file" @get="(val)=>payload.file=val" name="File" placeholder="Sesi 1" />
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
      payload: { title: "", type: "", file: "" },
      list: [
        { id: "Materi", value: "Materi" },
        { id: "Source Code", value: "Source Code" },
        { id: "Recording", value: "Recording" },
        { id: "Tugas", value: "Tugas" },
      ],
    };
  },
  methods: {
    submit() {
      alert(JSON.stringify(this.payload));
    },
  },
};
</script>