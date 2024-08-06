<template>
  <div class="sidebar-cont p-3 d-flex justify-content-between">
    <div class="sidebar-logo" :style="{ color: bindIconColor }">CL</div>
    <div class="list-div" v-if="!showAllIcon" @mouseenter="showAllIcon = true">
      <b-icon
        icon="list"
        :style="{ fill: bindIconColor }"
        class="pointer"
      ></b-icon>
    </div>
    <div
      v-else
      class="d-flex flex-column gap-25 list-div"
      :style="{ color: bindIconColor }"
      @mouseleave="showAllIcon = false"
    >
      <b-icon
        icon="person-fill"
        v-b-tooltip.hover.right="'About Me'"
        class="pointer"
        @click="goToConatiner('about-me')"
      ></b-icon>
      <b-icon
        class="pointer"
        icon="briefcase-fill"
        v-b-tooltip.hover.right="'Work Experience'"
        @click="goToConatiner('work-exp')"
      ></b-icon>
      <b-icon
        class="pointer"
        icon="file-earmark-text-fill"
        v-b-tooltip.hover.right="'Education'"
        @click="goToConatiner('education')"
      ></b-icon>
      <b-icon
        class="pointer"
        icon="award-fill"
        v-b-tooltip.hover.right="'Skills'"
        @click="goToConatiner('skills')"
      ></b-icon>
      <b-icon
        class="pointer"
        icon="type"
        v-b-tooltip.hover.right="'Languges known'"
        @click="goToConatiner('languages')"
      ></b-icon>
      <b-icon
        class="pointer"
        icon="telegram"
        v-b-tooltip.hover.right="'Contact'"
        @click="goToConatiner('contact')"
      ></b-icon>
    </div>
    <div
      v-if="themeColor == 'black'"
      @click="themeChange('white')"
      class="pointer"
    >
      <b-icon icon="moon-fill" :style="{ fill: bindIconColor }"></b-icon>
    </div>
    <div
      v-if="themeColor == 'white'"
      @click="themeChange('black')"
      class="pointer"
    >
      <b-icon icon="sun-fill"></b-icon>
    </div>
  </div>
</template>
<script>
export default {
  name: "Sidebar",
  components: {},
  mixins: [],
  props: {
    themeColor: String,
    bindIconColor: String,
  },
  data() {
    return {
      showAllIcon: false,
    };
  },
  computed: {},
  watch: {},
  created() {},
  mounted() {},
  methods: {
    themeChange(data) {
      this.$emit("theme-change", data);
    },
    goToConatiner(data) {
      document.getElementById(data).scrollIntoView({ behavior: "smooth" });
    },
  },
};
</script>
<style>
.sidebar-logo {
  color: white;
}

.sidebar-cont {
  height: 100vh;
  flex-direction: column;
}

@media screen and (max-width: 990px) {
  .sidebar-cont {
    flex-direction: row;
    width: 100vw;
    height: unset;
    height: 70px;
  }

  .list-div {
    display: none;
  }
}
</style>
