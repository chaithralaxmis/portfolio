<template>
  <div>
    <div class="home-left">
      <Sidebar
        :themeColor="themeColor"
        @theme-change="themeChange"
        :bindIconColor="bindIconColor"
      />
    </div>
    <b-container>
      <div class="home-right">
        <div class="profile-images">
          <img src="../assets/img/profile1.jpg" alt="" />
          <img src="../assets/img/prodile2.jpg" alt="" />
        </div>
        <div class="name mt-3 home-name" :style="{ color: bindIconColor }">
          <img src="../assets/img/name.svg" alt="" />
        </div>
        <div
          class="mt-3 h-60"
          :class="
            themeColor == 'white' ? 'typewriter-light' : 'typewriter-dark'
          "
        >
          <typewriter :type-interval="100" :replace-interval="1000">
            <span class="const">const</span>
            <span class="type-white"> skills</span>
            <span class="const"> =</span>
            <span class="type-white"> [</span> <br />
            <span class="skills"> 'HTML', 'CSS', 'Javascript', 'Vue js' </span
            ><span class="type-white">];</span>
          </typewriter>
        </div>

        <div
          class="d-flex justify-content-center align-items-center gap-25 mt-3"
        >
          <b-icon
            icon="linkedin"
            class="linkedin-icon"
            font-scale="2"
            @click="goToLinkedIn()"
          ></b-icon>
          <div
            class="instagram-icon-div d-flex align-items-center justify-content-center"
            @click="goToInstagram()"
          >
            <b-icon
              icon="instagram"
              class="instagram-icon"
              font-scale="2"
            ></b-icon>
          </div>
          <b-icon
            @click="goToGithub()"
            icon="github"
            :style="{ color: bindIconColor }"
            font-scale="2"
          ></b-icon>
        </div>

        <section
          id="about-me"
          name="about-me"
          class="about-me mt-5 d-flex justify-content-between text-start mb-5"
          :style="{ color: bindIconColor }"
        >
          <div class="section-heading">
            <b-icon icon="person-fill"></b-icon> ABOUT ME
          </div>
          <div class="section-content">
            Hello! I'm Chaithralaxmi S Shanbog, a passionate and innovative
            Developer dedicated to creating impactful digital experiences.
            Welcome to my portfolio website! <br />
            <br />
            This space is designed to showcase my skills, projects, and future
            aspirations. While you might notice that this particular section is
            a bit more casual, I assure you it reflects my genuine enthusiasm
            and dedication to my craft. With a strong foundation in [HTML, CSS,
            Javascript, Vuejs ], I strive to develop solutions that are not only
            technically sound but also user-friendly and visually appealing. My
            approach combines creativity with analytical thinking, allowing me
            to tackle complex challenges and deliver results that exceed
            expectations. <br />
            <br />
            I believe that great work speaks for itself, but I’m always eager to
            connect with like-minded professionals and potential collaborators.
            If you find my work intriguing and would like to discuss
            opportunities, share ideas, or just say hi, feel free to reach out
            via the contact section below. I’m excited to hear from you! Thank
            you for visiting, and I hope you enjoy exploring my portfolio!
          </div>
        </section>
        <div
          class="d-flex column-design mt-5 mb-5"
          :style="{ color: bindIconColor }"
        >
          <section
            id="work-exp"
            name="work-experience"
            class="position-relative timeline-section"
          >
            <div class="exp-section-heading">
              <b-icon icon="briefcase-fill"></b-icon> WORK EXPERIENCE
            </div>
            <div class="exp-section-content">
              <TimeLine :value="experience" />
            </div>
          </section>
          <section
            id="education"
            name="education-details"
            class="position-relative timeline-section"
          >
            <div class="exp-section-heading">
              <b-icon icon="file-earmark-text-fill"></b-icon> EDUCATION
            </div>
            <div class="exp-section-content">
              <TimeLine :value="education" />
            </div>
          </section>
        </div>
        <section
          id="skills"
          name="skills"
          class="mt-5 mb-5 text-start"
          :style="{ color: bindIconColor }"
        >
          <div class="section-heading my-3">
            <b-icon icon="award-fill"></b-icon> SKILLS
          </div>
          <div class="skill-section-content d-flex flex-wrap">
            <div
              class="skill-card d-flex align-items-center p-2"
              :style="{ 'border-color': bindIconColor, color: bindIconColor }"
            >
              <div>
                <b-icon icon="person-fill"></b-icon>
              </div>
              <div>
                <div>Web Design & Development</div>
                <div class="mt-2">(Html, CSS, Javascript)</div>
              </div>
            </div>
            <div
              class="skill-card d-flex align-items-center p-2"
              :style="{ 'border-color': bindIconColor, color: bindIconColor }"
            >
              <div>
                <b-icon icon="person-fill"></b-icon>
              </div>
              <div>
                <div>Frontend Javascript Frameworks</div>
                <div class="mt-2">(Vue js)</div>
              </div>
            </div>
          </div>
        </section>
        <section
          id="languages"
          name="languages"
          class="text-start mb-5 mt-5"
          :style="{ color: bindIconColor }"
        >
          <div class="section-heading my-3">
            <b-icon icon="type"></b-icon> Languages
          </div>

          <div
            class="skill-section-content text-start"
            :style="{ color: bindIconColor }"
          >
            <div class="mt-3">
              <TypeWritter :dispArray="langauges" />
            </div>
            <div :style="{ color: bindIconColor }">
              Kannada <span class="mx-2">/</span> English
              <span class="mx-2">/</span> Hindi
              <span class="mx-2">/</span> Konkani
            </div>
          </div>
        </section>
        <section
          id="contact"
          name="contact"
          class="text-start mb-5 mt-5"
          :class="
            this.themeColor == 'white'
              ? ' contact-form-light'
              : ' contact-form-dark'
          "
          :style="{ color: bindIconColor }"
        >
          <div class="section-heading my-3">
            <b-icon icon="telegram"></b-icon> Contact
          </div>

          <div>
            <b-row>
              <b-col lg="6" md="6" sm="12">
                <b-form-group class="mb-4">
                  <label for="name">Full Name</label>
                  <b-form-input
                    name="name"
                    type="text"
                    placeholder="Enter name"
                    v-model="form.name"
                  ></b-form-input>
                  <div>The one where you will tell me your name</div>
                </b-form-group>
              </b-col>
            </b-row>
            <b-row>
              <b-col lg="6" md="6" sm="12">
                <b-form-group class="mb-4">
                  <label for="name">Email ID</label>
                  <b-form-input
                    name="email"
                    type="text"
                    placeholder="Enter email"
                    v-model="form.email"
                  ></b-form-input>
                  <div>
                    The one where you will tell me how can I contact you back
                  </div>
                </b-form-group>
              </b-col>
            </b-row>
            <b-row>
              <b-col lg="9" md="9" sm="12">
                <b-form-group class="mb-4">
                  <label for="name">Message</label>
                  <b-form-textarea
                    name="name"
                    type="textarea"
                    placeholder="Type your message here"
                    rows="4"
                    max-rows="4"
                    v-model="form.message"
                  ></b-form-textarea>
                  <div>
                    The one where you will tell me what I can do to help you
                  </div>
                </b-form-group>
              </b-col>
            </b-row>

            <b-button
              :class="
                themeColor == 'white' ? 'black-send-btn' : 'white-send-btn'
              "
              @click="submitForm"
              >Send Message</b-button
            >
          </div>
        </section>
      </div>
    </b-container>
  </div>
</template>
<script>
import Sidebar from "../components/sidebar.vue";
import Typewriter from "typewriter-vue";
import TimeLine from "../components/timeline.vue";
import TypeWritter from "@/components/TypeWritter.vue";
export default {
  name: "Home",
  components: {
    Sidebar,
    Typewriter,
    TimeLine,
    TypeWritter,
  },
  mixins: [],
  props: {},
  data() {
    return {
      formUrl:
        "https://docs.google.com/forms/d/e/1FAIpQLSeyZjailYao2-9Si0fwcajV1c4mUdGGFokJCXGsJWlb-mA3eA/viewform?embedded=true",
      themeColor: "black",
      langauges: [
        "ನನ್ನ ಭಾಷೆ ನನ್ನ ಹೆಮ್ಮೆ",
        "I'm pretty fluent in English.",
        "मैं हिंदी में बात करने की कोशिश करूंगी।",
        "Migele matrubashe konkani",
      ],
      form: {
        name: "",
        email: "",
        message: "",
      },
      education: [
        {
          title: "Moodlakatte Institue Of Technology",
          year: "2017 - 2021",
          degree: "Bachelor Of Engineering (B.E)",
          location: "Kundapura, Karnataka",
        },
        {
          title: "Holy Redeemer Composite PU College",
          year: "2017",
          degree: "Higher Secondary Education",
          location: "Hosanagara, Karnataka",
        },
        {
          title: "Sri Ramakrishna Vidyalaya",
          year: "2015",
          degree: "Secondary Education",
          location: "Hosanagara, Karnataka",
        },
      ],
      experience: [
        {
          title: "Hire3x",
          year: "2021 - Present",
          degree: "Sofware Developer",
          location: "Bangalore, Karnataka",
        },
      ],
    };
  },
  computed: {
    bindIconColor() {
      return this.themeColor == "white" ? "black" : "white";
    },
  },
  watch: {},
  created() {
    this.themeChange(this.themeColor);
  },
  mounted() {
    window.scrollTo(0, 0);
  },
  methods: {
    themeChange(data) {
      this.themeColor = data;
      document.body.style.backgroundColor = this.themeColor;
    },
    async submitForm() {
      try {
        const formData = new URLSearchParams();
        formData.append("entry.1040639414", this.form.name); // Name field
        formData.append("entry.1826715814", this.form.email); // Email field
        formData.append("entry.1380458988", this.form.message); // Message field

        const response = await fetch(
          "https://script.google.com/macros/s/AKfycbxQjBm9ktpR5xxUaFNgxQsdUGyt28XRDUQbIF-9Rkg493yn-z6Gf-VSBfHeFcUV7I1i/exec",
          {
            method: "POST",
            body: formData,
            headers: {
              "Content-Type": "application/x-www-form-urlencoded",
            },
          }
        );

        if (response.ok) {
          this.form = {
            name: "",
            email: "",
            message: "",
          };
          alert("Form submitted successfully!");
        } else {
          const errorText = await response.text();
          console.error("Submission failed:", errorText);
          alert("Form submission failed.");
        }
      } catch (error) {
        console.error("Error:", error);
        alert("Error submitting form.");
      }
    },
    goToLinkedIn() {
      window.open(
        "https://www.linkedin.com/in/chaithralaxmi-s-shanbog-22b527213/"
      );
    },
    goToGithub() {
      window.open("https://github.com/chaithralaxmis?tab=repositories");
    },
    goToInstagram() {
      window.open(
        "https://www.instagram.com/chaithralaxmi_s_shanbag/?igsh=MXRvZWZkaDU0anNxbQ%3D%3D"
      );
    },
  },
};
</script>
<style>
.timeline-section {
  width: 50%;
}
.contact-form-dark .form-control {
  background: transparent !important;
  color: white !important;
  border: 2px solid #4c4141;
}
.contact-form-dark .form-control:focus {
  border-color: unset;
  border: 2px solid;
  box-shadow: unset;
}
.contact-form-dark .form-control::placeholder {
  color: white !important;
}

.home-left {
  position: fixed;
  left: 0;
  top: 0;
}

.home-right {
  width: 100%;
  padding: 10rem 0rem;
}

.profile-images {
  height: 300px;
}

.profile-images img {
  height: 100%;
  width: 200px;
}

.const {
  color: #3b82f6;
}

.skills {
  color: #ef4444;
}

.about-me {
  flex-direction: row;
}

.section-heading {
  width: 20%;
  font-weight: var(--weight-B);
  font-size: var(--font-sec-heading);
}

.exp-section-heading {
  position: absolute;
  font-weight: var(--weight-B);
  font-size: var(--font-sec-heading);
  /* left: 19%; */
  left: -1%;
}

.exp-section-content {
  top: 25px;
  position: relative;
}

.section-content {
  width: 80%;
}

.skill-section-content {
  width: 100%;
  gap: 20px;
}

.column-design {
  gap: 0px;
}

.skill-card {
  border: 1px solid;
  width: 19%;
  height: 80px;
  gap: 20px;
}
.black-send-btn {
  background: black !important;
  color: white !important;
}
.white-send-btn {
  background: white !important;
  color: black !important;
}

@media screen and (max-width: 990px) {
  .home-name img {
    width: 100%;
  }
  .about-me {
    flex-direction: column;
  }

  .profile-images img {
    height: 100%;
    width: 150px;
  }

  .home-right {
    width: 100%;
    padding: 7rem 1rem;
  }

  .section-heading {
    width: unset;
    margin-bottom: 1rem;
  }

  .section-content {
    width: unset;
  }

  .column-design {
    flex-wrap: wrap;
    gap: 50px !important;
  }

  .timeline-section {
    width: 100%;
  }
}

@media screen and (max-width: 800px) {
  .skill-card {
    width: 100%;
    /* Full width on screens up to 800px */
  }
}

@media screen and (min-width: 801px) and (max-width: 1200px) {
  .skill-card {
    width: 48%;
    /* Two cards per row from 801px to 1200px */
  }
}

@media screen and (min-width: 1201px) and (max-width: 1480px) {
  .skill-card {
    width: 32%;
    /* Three cards per row from 1201px to 1480px */
  }
}

@media screen and (min-width: 1481px) and (max-width: 1630px) {
  .skill-card {
    width: 23%;
    /* Four cards per row from 1481px to 1630px */
  }
}

/* For screens larger than 1630px */
@media screen and (min-width: 1631px) {
  .skill-card {
    width: 22%;
    /* Five cards per row for screens wider than 1630px */
  }
}
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans+Kannada:wght@400;700&display=swap");

body {
  font-family: "Noto Sans Kannada", sans-serif;
}
.typewriter-dark .type-white {
  color: white;
}

.linkedin-icon {
  color: rgb(10, 102, 194);
  background: white;
  border-radius: 10px;
}

.instagram-icon {
  background: rgb(225 48 108);
  color: white;
  border-radius: 10px;
}
.instagram-icon-div {
  background: rgb(225 48 108);
  padding: 2px;
  border-radius: 10px;
}
</style>
