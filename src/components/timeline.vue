<template>
  <div class="timeline">
    <div
      class="timeline-container right"
      v-for="(data, index) in value"
      :key="index"
    >
      <div class="timeline-content">
        <h4>{{ data.title }}</h4>
        <div>
          {{ data.year }}
        </div>
        <div>
          {{ data.degree }}
        </div>
        <div>{{ data.location }}</div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Timeline",
  components: {},
  mixins: [],
  props: {
    value: Array,
  },
  data() {
    return {};
  },
  computed: {},
  watch: {},
  mounted() {},
  methods: {},
};
</script>
<style>
/* The actual timeline (the vertical ruler) */
.timeline {
  position: relative;
  max-width: 1200px;
  margin: 0 auto;
}

/* The actual timeline (the vertical ruler) */
.timeline::after {
  content: "";
  position: absolute;
  width: 6px;
  background-color: #73737340;
  top: 0;
  bottom: 0;
  /* left: 20%; */
  left: 1%;
  margin-left: -3px;
}

/* Container around content */
.timeline-container {
  padding: 10px 40px;
  position: relative;
  background-color: inherit;
  width: 100%;
}

/* The circles on the timeline */
.timeline-container::after {
  content: "";
  position: absolute;
  width: 20px;
  height: 20px;
  /* right: -17px; */
  background-color: white;
  border: 4px solid #ff9f55;
  top: 15px;
  border-radius: 50%;
  z-index: 1;
}

/* Place the container to the left */
.left {
  left: 0;
}

/* Place the container to the right */
/* .right {
  left: 20%;
} */

/* Add arrows to the left container (pointing right) */
.left::before {
  content: " ";
  height: 0;
  position: absolute;
  top: 22px;
  width: 0;
  z-index: 1;
  right: 30px;
  /* border: medium solid white; */
  border-width: 10px 0 10px 10px;
  /* border-color: transparent transparent transparent white; */
}

/* Add arrows to the right container (pointing left) */
.right::before {
  content: " ";
  height: 0;
  position: absolute;
  top: 22px;
  width: 0;
  z-index: 1;
  left: 30px;
  /* border: medium solid white; */
  border-width: 10px 10px 10px 0;
  /* border-color: transparent white transparent transparent; */
}

/* Fix the circle for containers on the right side */
.right::after {
  left: -4px;
}

/* The actual content */
.timeline-content {
  padding: 20px 30px;
  /* background-color: white; */
  position: relative;
  border-radius: 6px;
  text-align: left;
}

/* Media queries - Responsive timeline on screens less than 600px wide */
@media screen and (max-width: 600px) {
  /* Place the timelime to the left */

  /* Full-width containers */
  .timeline-container {
    width: 100%;
    padding-left: 70px;
    padding-right: 25px;
  }

  /* Make sure that all arrows are pointing leftwards */
  .timeline-container::before {
    left: 60px;
    /* border: medium solid white; */
    border-width: 10px 10px 10px 0;
    /* border-color: transparent white transparent transparent; */
  }

  /* Make sure all circles are at the same spot */
  .left::after,
  .right::after {
    left: -3px;
  }

  /* Make all right containers behave like the left ones */
  .right {
    left: 0%;
    padding-left: 40px;
  }
  .timeline::after {
    left: 2%;
  }
}
</style>
