<template>
  <div>
    <div class="card shadow rounded">
      <img class="card-img-top pointer" :src="img" srcset="https://shiftacademy.id/wp-content/uploads/2019/07/Logo-Shift-Academy-with-Circle.png" :alt="title" data-toggle="modal" :data-target="`#${id}`" data-backdrop="">
      <div class="card-body">
        <hr>
        <h5 class="card-title text-capitalize pointer" data-toggle="modal" :data-target="`#${id}`" data-backdrop="">{{title}}</h5>
        <div class="d-flex justify-content-between align-items-center">
          <button v-if="!joined" type="button" @click="canIJoin" class="btn btn-primary btn-sm">Gabung Kelas</button>
          <button v-else @click="redirectToClass" class="btn">Lihat Kelas</button>
          <span v-if="joined" class="d-inline-block" tabindex="0" data-toggle="tooltip" :title="'Keluar dari kelas '+title">
            <i class="fas fa-sign-out-alt text-warning pointer" @click="canILeave"></i>
          </span>
        </div>
      </div>
    </div>

    <div class="modal fade" :id="`${id}`" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
      <div class="modal-dialog modal-xl modal-dialog-centered modal-dialog-scrollable">
        <div class="modal-content">
          <div class="modal-header">
            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
          <div class="modal-body">
            <div class="row">
              <div class="col-md-4 border-right border-black">
                <img class="w-100" :src="img" srcset="https://shiftacademy.id/wp-content/uploads/2019/07/Logo-Shift-Academy-with-Circle.png" alt="...">
              </div>
              <div class="col-md-8">
                <h5 class="text-capitalize">{{title}}</h5>
                <ul class="nav nav-pills mb-3" id="pills-tab" role="tablist">
                  <li class="nav-item" role="presentation">
                    <a class="nav-link active" :id="`pills-${id}-desc-tabs`" data-toggle="pill" :href="`#pills-${id}-desc`" role="tab" aria-controls="pills-home" aria-selected="true">Deskripsi</a>
                  </li>
                  <li class="nav-item" role="presentation">
                    <a class="nav-link" :id="`pilsl-${id}-jadwal-tabs`" data-toggle="pill" :href="`#pills-${id}-jadwal`" role="tab" aria-controls="pills-profile" aria-selected="false">Jadwal</a>
                  </li>
                </ul>
                <div class="tab-content" id="pills-tabContent">
                  <div class="tab-pane fade show active" :id="`pills-${id}-desc`" role="tabpanel" :aria-labelledby="`pill-${id}-desc-tabs`">
                    <p class="text-justify">{{desc}}</p>
                  </div>
                  <div class="tab-pane fade" :id="`pills-${id}-jadwal`" role="tabpanel" :aria-labelledby="`pill-${id}-profile-tabs`">
                    <table>
                      <tbody>
                        <tr>
                          <td width="100">Mulai</td>
                          <td>19 Agustus 2021</td>
                        </tr>
                        <tr>
                          <td>Selesai</td>
                          <td>19 Desember 2021</td>
                        </tr>
                      </tbody>
                    </table>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-dismiss="modal">Tutup</button>
            <button type="button" v-if="!joined" @click="canIJoin" class="btn btn-primary">Gabung Kelas</button>
            <button v-else @click="redirectToClass" class="btn btn-primary">Lihat Kelas</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    title: String,
    desc: String,
    img: String,
    joined: {
      type: Boolean,
      default: true,
    },
  },
  computed: {
    id() {
      return this.title.replace(/ /g, "");
    },
  },
  methods: {
    async canIJoin() {
      const { value } = await this.$swal({
        title: "Apakah Kamu yakin?",
        text: `Berkomitmen untuk bergabung pada kelas ${this.title}`,
        icon: "question",
        showCancelButton: true,
      });
      if (value) this.yesJoin();
    },
    yesJoin() {
      this.$swal({
        icon: "success",
        title: "Selamat...",
        text: "Kamu siap belajar di kelas " + this.title,
      });
    },
    async canILeave() {
      const { value } = await this.$swal({
        title: "Apakah Kamu yakin?",
        text: `Keluar dari kelas ${this.title}`,
        icon: "question",
        showCancelButton: true,
      });
      if (value) this.yesLeave();
    },
    yesLeave() {
      this.$swal({
        icon: "success",
        title: "Yaaah...",
        text: "Terima kasih telah menjadi student di kelas " + this.title,
      });
    },
    redirectToClass() {
      $("body").removeClass("modal-open");
      this.$router.push(`/${this.id}/kelas`);
    },
  },
};
</script>