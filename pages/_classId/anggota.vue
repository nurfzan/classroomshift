<template>
  <div class="container">
    <h4>Tutor & SPV</h4>
    <hr>
    <div class="row">
      <div class="col-sm-4 col-md-3 col-6" v-for="(tutor,i) in tutors" :key="i">
        <anggota />
      </div>
    </div>

    <h4>Student</h4>
    <hr>
    <div class="row">
      <div class="col-sm-4 col-md-3 col-6" v-for="(student,i) in students" :key="i">
        <anggota />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      tutors: [{}, {}],
      students: [{}, {}, {}, {}, {}, {}, {}, {}, {}],
    };
  },
};
</script>