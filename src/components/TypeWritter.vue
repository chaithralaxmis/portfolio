<template>
  <div class="typing-container">
    <span class="typing-text">{{ displayedText }}</span>
    <span class="cursor"></span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      textToType: "",
      displayedText: "",
      typingSpeed: 100, // typing speed in milliseconds
      index: 0,
      arrayIndex: 0,
    };
  },
  props: {
    dispArray: {
      type: Array,
      default: () => [],
    },
  },
  mounted() {
    this.startTyping();
  },
  methods: {
    startTyping() {
      this.typingInterval = setInterval(() => {
        if (this.index < this.textToType.length) {
          this.displayedText += this.textToType[this.index];
          this.index++;
        } else {
          // Move to the next item in the array
          this.arrayIndex = (this.arrayIndex + 1) % this.dispArray.length;
          this.textToType = this.dispArray[this.arrayIndex];
          this.displayedText = "";
          this.index = 0;
        }
      }, this.typingSpeed);

      // Start typing the first text
      if (this.dispArray.length > 0) {
        this.textToType = this.dispArray[this.arrayIndex];
      }
    },
  },
};
</script>

<style scoped>
.typing-container {
  display: inline-flex;
  align-items: center;
  font-family: "Courier New", Courier, monospace;
}

.typing-text {
  border-right: 2px solid black; /* Space for the cursor */
  padding-right: 5px;
}

.cursor {
  width: 2px; /* Width of the cursor */
  height: 1.2em; /* Height of the cursor (should match line height) */
  background-color: white;
  animation: blink-caret 0.75s step-end infinite;
}

@keyframes blink-caret {
  50% {
    background-color: transparent;
  }
}
</style>
