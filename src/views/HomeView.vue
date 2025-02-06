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
          <img
            src="../assets/img/chaithralakshmi.jpg"
            alt=""
            class="first-img"
          />

          <img
            src="../assets/img/chaithralakshmi2.jpg"
            alt=""
            class="second-img"
          />
          <img
            src="../assets/img/chaithralakshmi3.jpg"
            alt=""
            class="second-img"
          />
        </div>
        <div class="name mt-3 home-name" :style="{ color: bindIconColor }">
          <img src="../assets/img/name.svg" alt="" />
        </div>
        <div
          class="mt-3 h-60 fs-14"
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
          <!-- <div
            class="instagram-icon-div d-flex align-items-center justify-content-center"
            @click="goToInstagram()"
          >
            <b-icon
              icon="instagram"
              class="instagram-icon"
              font-scale="2"
            ></b-icon>
          </div> -->
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
          <div
            class="section-heading fs-14"
            :style="{ color: bindIconBlackColor }"
          >
            <b-icon icon="person-fill"></b-icon> ABOUT ME
          </div>

          <div class="section-content fs-14">
            <p>Hello!</p>
            I'm Chaithralaxmi S Shanbog, a passionate and innovative Developer
            dedicated to creating impactful digital experiences. Welcome to my
            portfolio website! <br />
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
            <div
              class="exp-section-heading fs-14"
              :style="{ color: bindIconBlackColor }"
            >
              <b-icon icon="briefcase-fill"></b-icon> WORK EXPERIENCE
            </div>
            <div class="exp-section-content">
              <TimeLine :value="experience" :themeColor="themeColor" />
            </div>
          </section>
          <section
            id="education"
            name="education-details"
            class="position-relative timeline-section"
          >
            <div
              class="exp-section-heading fs-14"
              :style="{ color: bindIconBlackColor }"
            >
              <b-icon icon="file-earmark-text-fill"></b-icon> EDUCATION
            </div>
            <div class="exp-section-content">
              <TimeLine :value="education" :themeColor="themeColor" />
            </div>
          </section>
        </div>
        <section
          id="skills"
          name="skills"
          class="mt-5 mb-5 text-start"
          :style="{ color: bindIconColor }"
        >
          <div
            class="section-heading fs-14 my-3"
            :style="{ color: bindIconBlackColor }"
          >
            <b-icon icon="award-fill"></b-icon> SKILLS
          </div>
          <div
            class="skill-section-content d-flex flex-wrap"
            :class="
              this.themeColor == 'white'
                ? ' skill-cards-light'
                : ' skill-cards-dark'
            "
          >
            <div
              class="skill-card d-flex align-items-center p-2"
              :style="{ color: bindIconColor }"
            >
              <div>
                <b-icon icon="award-fill"></b-icon>
              </div>
              <div>
                <div class="skill-heading fs-14">Web Design & Development</div>
                <div class="mt-2 skill-text fs-12">(Html, CSS, Javascript)</div>
              </div>
            </div>
            <div
              class="skill-card d-flex align-items-center p-2"
              :style="{ color: bindIconColor }"
            >
              <div>
                <b-icon icon="award-fill"></b-icon>
              </div>
              <div>
                <div class="skill-heading fs-14">
                  Frontend Javascript Frameworks
                </div>
                <div class="mt-2 skill-text fs-12">(Vue js)</div>
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
          <div
            class="section-heading fs-14 my-3"
            :style="{ color: bindIconBlackColor }"
          >
            <b-icon icon="type"></b-icon> Languages
          </div>

          <div
            class="skill-section-content text-start"
            :style="{ color: bindIconColor }"
          >
            <div
              class="mt-5 language-texts fs-18"
              :style="{ color: bindIconBlackColor }"
            >
              <TypeWritter :dispArray="langauges" />
            </div>
            <div :style="{ color: bindIconColor }" class="mt-5 fs-12">
              Kannada <span class="mx-2">/</span> English
              <span class="mx-2">/</span> Hindi
              <span class="mx-2">/</span> Konkani
            </div>
          </div>
        </section>
        <section
          id="resume"
          name="resume"
          class="text-start mb-5 mt-5"
          :style="{ color: bindIconColor }"
        >
          <div
            class="section-heading fs-14 my-3 list-div"
            :style="{ color: bindIconBlackColor }"
          >
            <b-icon icon="file-earmark-text-fill"></b-icon> Resume
          </div>
          <div
            class="skill-section-content resume-section-content text-start d-flex justify-content-between list-div "
            :style="{ color: bindIconColor }"
          >
            <b-overlay :show="resumeHover" class="overlay-resume">
              <div
                @mouseenter="resumeHover = true"
                @mouseleave="resumeHover = false"
                class="resume-container pointer"
                :class="
                  resumeHover
                    ? 'haze-hover'
                    : themeColor == 'white'
                    ? 'white-resume-container'
                    : ''
                "
                @click="goToHire3xResume()"
              >
                <img
                  src="@/assets/img/resume1.png"
                  alt="resume1"
                  class="h-100"
                />
                <img
                  src="@/assets/img/resume2.jpg"
                  alt="resume2"
                  class="h-100 resume2"
                />

                <!-- Show the arrows-fullscreen icon instead of the spinner -->
                <b-icon
                  :style="{ color: 'black' }"
                  v-if="resumeHover"
                  icon="arrows-fullscreen"
                  class="hover-icon"
                ></b-icon>
              </div>
            </b-overlay>

            <div class=" resume-subtext">
              To those HRs out there who need a more organized and minimal
              version of my information, you can download the trusted PDF
              version here:
            </div>
          </div>
        </section>
        <section
          id="contact"
          name="contact"
          class="text-start mb-5 mt-5"
          :class="
            themeColor == 'white' ? ' contact-form-light' : ' contact-form-dark'
          "
          :style="{ color: bindIconColor }"
        >
          <div
            class="section-heading fs-14 my-5"
            :style="{ color: bindIconBlackColor }"
          >
            <b-icon icon="telegram"></b-icon> Contact
          </div>

          <div>
            <b-row>
              <b-col lg="6" md="6" sm="12">
                <b-form-group class="mb-4">
                  <label
                    for="name"
                    class="contact-heading fs-12"
                    :style="{ color: bindIconBlackColor }"
                    >Full Name</label
                  >
                  <b-form-input
                    name="name"
                    type="text"
                    placeholder="Enter name"
                    v-model="form.name"
                  ></b-form-input>
                  <div class="fs-10 error" v-if="$v.form.name.$dirty && !$v.form.name.required">Required</div>
                  <div class="fs-12 mt-1" v-else>
                    The one where you will tell me your name
                  </div>
                </b-form-group>
              </b-col>
            </b-row>
            <b-row>
              <b-col lg="6" md="6" sm="12">
                <b-form-group class="mb-4">
                  <label
                    for="name"
                    class="contact-heading fs-12"
                    :style="{ color: bindIconBlackColor }"
                    >Email ID</label
                  >
                  <b-form-input
                    name="email"
                    type="text"
                    placeholder="Enter email"
                    v-model="form.email"
                  ></b-form-input>
                  <div class="fs-10 error" v-if="$v.form.email.$dirty && !$v.form.email.required">Required</div>
                  <div class="fs-10 error" v-else-if="$v.form.email.required && !$v.form.email.email">Enter proer email address</div>
                  <div class="fs-12 mt-1" v-else >
                    The one where you will tell me how can I contact you back
                  </div>
                </b-form-group>
              </b-col>
            </b-row>
            <b-row>
              <b-col lg="9" md="9" sm="12">
                <b-form-group class="mb-4">
                  <label
                    for="name"
                    class="contact-heading fs-12"
                    :style="{ color: bindIconBlackColor }"
                    >Message</label
                  >
                  <b-form-textarea
                    name="name"
                    type="textarea"
                    placeholder="Type your message here"
                    rows="4"
                    max-rows="4"
                    v-model="form.message"
                  ></b-form-textarea>
                  <div class="fs-10 error" v-if="$v.form.message.$dirty && !$v.form.message.required">
                    Required
                  </div>
                  <div class="fs-12 mt-1" v-else>
                    The one where you will tell me what I can do to help you
                  </div>
                </b-form-group>
              </b-col>
            </b-row>

            <b-button
              :class="
                themeColor == 'white' ? 'black-send-btn' : 'white-send-btn'
              "
              class="fs-14 cta"
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
import { required } from "vuelidate/lib/validators";
import { email } from "vuelidate/lib/validators";
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
      resumeHover: false,
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
  validations: {
  
    form:{

      name: { required },
      email: { required,email },
      message: { required },
    }
    
  },
  computed: {
    bindIconColor() {
      return this.themeColor == "white" ? "#404040" : "white";
    },
    bindIconBlackColor() {
      return this.themeColor == "white" ? "#171717" : "white";
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
    goToHire3xResume() {
      window.open("https://candidate.hire3x.com/u/Chaithralaxmi");
    },
    themeChange(data) {
      this.themeColor = data;
      document.body.style.backgroundColor = this.themeColor;
    },
    async submitForm() {
      this.$v.$touch();
      if (!this.$v.$invalid) {
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
            this.$v.$reset();
          }
        } catch (error) {
          console.error("Error:", error);
          alert("Error submitting form.");
        }
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
.contact-form-light .form-control {
  border: 1.4px solid #8e8888;
  font-size: 13px;
}
.form-control:focus {
  box-shadow: unset !important;
}
.contact-form-dark .form-control {
  background: transparent !important;
  color: white !important;
  border: 2px solid #e3e3e35e;
  font-size: 13px;
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
  padding: 8rem 0rem;
}

.profile-images {
  height: 250px;
}

.profile-images img {
  height: 100%;
  width: 160px;
}
.profile-images img:hover {
  width: 226px; /* Shrink width on hover */
  transform: scale(
    1.1
  ); /* Optional: slightly scale the image to make it more dynamic */
  animation-delay: 1.5s; /* If you're using an animation with delay */
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
  /* left: -1%; */
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
  width: 19%;
  height: 80px;
  gap: 20px;
}

.skill-cards-light .skill-card {
  border: 1.5px solid #8e8888 !important;
}

.skill-cards-dark .skill-card {
  border: 2px solid #e3e3e35e !important;
}

.black-send-btn {
  background: #495057 !important;
  color: white !important;
  padding: 3px 8px !important;
}
.white-send-btn {
  background: white !important;
  color: black !important;
  padding: 3px 8px !important;
}
.resume-subtext{
    width: 50%;
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
  .overlay-resume{
    order:1;
  }
  .resume-section-content{
    flex-wrap: wrap;
  }
  .resume-subtext{
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
    width: 24%;
    /* Four cards per row from 1481px to 1630px */
  }
}

/* For screens larger than 1630px */
@media screen and (min-width: 1631px) {
  .skill-card {
    width: 24%;
    /* Five cards per row for screens wider than 1630px */
  }
}

@media (max-width: 768px) {
  .resume2{
    display: none
  }
  .profile-images{
    overflow: scroll !important
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
.skill-heading {
  font-weight: var(--weight-M);
}

.skill-text {
  font-size: 14px;
}

.language-texts {
  height: 30px;
}
.profile-images {
  display: flex; /* Align images side by side */
  justify-content: center; /* Center the images horizontally */
  gap: 10px; /* Add a gap between the images */
  width: 100%; /* Or any fixed width if required */
  height: 400px; /* Adjust to the size of your images */
  overflow: hidden;
}

.profile-images img {
  height: 100%; /* Ensure images take up the container height */
  opacity: 0; /* Initially hide the images */
  animation: slideIn 2s forwards; /* Apply the slide-in animation */
}

.profile-images img:nth-child(2) {
  animation-delay: 2s; /* Delay the second image by 2 seconds */
}
.profile-images img:nth-child(3) {
  animation-delay: 4s; /* Delay the second image by 2 seconds */
}

@keyframes slideIn {
  0% {
    transform: translatey(-100%); /* Start off-screen on the left */
    opacity: 0;
  }
  100% {
    transform: translateX(0); /* End in the original position */
    opacity: 1;
  }
}

.resume-container {
  height: 300px;
  width: fit-content;
}
.haze-hover::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 2;
  background-color: #000000;
  backdrop-filter: blur(1px);
  opacity: 0.2;
  border-radius: 5px;
}
.b-overlay,
.b-overlay-wrap {
  width: fit-content !important;
}
.b-overlay .spinner-border {
  display: none;
}
.hover-icon {
  color: black;
  position: absolute;
  left: 49%;
  top: 50%;
}

.white-send-btn {
  box-shadow: 5px 5px rgba(255, 255, 255, 0.3); /* Default shadow */
  transform: skewX(-12deg);
}
.black-send-btn {
  box-shadow: 5px 5px rgba(1, 1, 1, 0.5); /* Default shadow */
  transform: skewX(-12deg);
}

.cta:focus {
  outline: none;
}

.cta:hover {
  transform: skewX(-15deg) translateY(8px) translateX(8px); /* Button raises on hover */
  box-shadow: 0px 0px 20px rgba(105, 0, 0, 0.2); /* Shadow shrinks on hover */
}

.cta span:nth-child(2) {
  transition: 0.5s;
  margin-right: 0px;
}

.cta:hover span:nth-child(2) {
  transition: 0.5s;
  margin-right: 45px;
}


/**************SVG****************/

path.one {
  transition: 0.4s;
  transform: translateX(-60%);
}

path.two {
  transition: 0.5s;
  transform: translateX(-30%);
}

.cta:hover path.three {
  animation: color_anim 1s infinite 0.2s;
}

.cta:hover path.one {
  transform: translateX(0%);
  animation: color_anim 1s infinite 0.6s;
}

.cta:hover path.two {
  transform: translateX(0%);
  animation: color_anim 1s infinite 0.4s;
}

/* SVG animations */
@keyframes color_anim {
  0% {
    fill: white;
  }
  50% {
    fill: #fbc638;
  }
  100% {
    fill: white;
  }
}
</style>
