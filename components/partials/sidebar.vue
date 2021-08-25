<template>
  <div class="main-sidebar">
    <aside id="sidebar-wrapper">
      <div class="sidebar-brand">
        <nuxt-link to="/">Fullstack Academy</nuxt-link>
      </div>
      <div class="sidebar-brand sidebar-brand-sm">
        <nuxt-link to="/">FA</nuxt-link>
      </div>
      <ul class="sidebar-menu">
        <li v-for="(menu,i) in menus" :key="i">
          <nuxt-link :to="menu.link" class="nav-link">
            <i :class="menu.icon" style="font-size:1.2em"></i> <span>{{menu.name}}</span>
          </nuxt-link>
        </li>
      </ul>
    </aside>
  </div>
</template>
<script>
export default {
  data() {
    return {
      menus: [
        { icon: "fab fa-dashcube", name: "Semua Kelas", link: "/" },
        { icon: "far fa-bookmark", name: "Kelasku", link: "/kelasku" },
        { icon: "far fa-id-badge", name: "Presensi", link: "/presensi" },
      ],
    };
  },
};
</script>