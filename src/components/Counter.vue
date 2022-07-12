<template>
  <main class="main-component">
    <section class="timer-section">
      <article class="heading-text-article">
        <header class="capital-letter coming-soon">we're launching soon</header>
      </article>
      <!-- timer article starts here -->
      <article class="counter-article-component">
        <div class="box-text-container">
          <div class="box">
            <!-- start here -->
            <div class="rotating-page-container">
              <div
                :class="[
                  flipDays ? 'rotating-page flip-page' : 'rotating-page',
                ]"
              >
                <p class="page front-page">
                  <span class="up-numbers">
                    {{ days }}
                  </span>
                </p>
                <p class="page back-page">
                  <span class="down-numbers">
                    {{ days }}
                  </span>
                </p>
              </div>
            </div>
            <!-- end here -->
            <div class="up-box">
              <p class="up-numbers">{{ days }}</p>
            </div>
            <div class="down-box">
              <p class="down-numbers">{{ days }}</p>
            </div>
          </div>
          <p>days</p>
        </div>
        <div class="box-text-container">
          <div class="box">
            <!-- start here -->
            <div class="rotating-page-container">
              <div
                :class="[
                  flipHours ? 'rotating-page flip-page' : 'rotating-page',
                ]"
              >
                <p class="page front-page">
                  <span class="up-numbers">
                    {{ hours }}
                  </span>
                </p>
                <p class="page back-page">
                  <span class="down-numbers">
                    {{ hours }}
                  </span>
                </p>
              </div>
            </div>
            <!-- end here -->
            <div class="up-box">
              <p class="up-numbers">{{ hours }}</p>
            </div>
            <div class="down-box">
              <p class="down-numbers">{{ hours }}</p>
            </div>
          </div>
          <p>hours</p>
        </div>
        <div class="box-text-container">
          <div class="box">
            <!-- start here -->
            <div class="rotating-page-container">
              <div
                :class="[
                  flipMinutes ? 'rotating-page flip-page' : 'rotating-page',
                ]"
              >
                <p class="page front-page">
                  <span class="up-numbers">
                    {{ minutes }}
                  </span>
                </p>
                <p class="page back-page">
                  <span class="down-numbers">
                    {{ minutes }}
                  </span>
                </p>
              </div>
            </div>
            <!-- end here -->
            <div class="up-box">
              <p class="up-numbers">{{ minutes }}</p>
            </div>
            <div class="down-box">
              <p class="down-numbers">{{ minutes }}</p>
            </div>
          </div>
          <p>minutes</p>
        </div>
        <div class="box-text-container">
          <div class="box">
            <!-- start here -->
            <div class="rotating-page-container">
              <div
                :class="[
                  flipSecond ? 'rotating-page flip-page' : 'rotating-page',
                ]"
              >
                <p class="page front-page">
                  <span class="up-numbers">
                    {{ seconds }}
                  </span>
                </p>
                <p class="page back-page">
                  <span class="down-numbers">
                    {{ seconds }}
                  </span>
                </p>
              </div>
            </div>
            <!-- end here -->
            <div class="up-box">
              <p class="up-numbers">{{ seconds }}</p>
              <p class="up-numbers">{{ seconds }}</p>
            </div>
            <div class="down-box">
              <p class="down-numbers">
                {{ seconds }}
              </p>
            </div>
          </div>
          <p>seconds</p>
        </div>
      </article>

      <!-- timer article ends here -->
    </section>
    <article class="social-hill-article">
      <div class="social-icons">
        <img src="../images/icon-facebook.svg" alt="" />
        <img src="../images/icon-pinterest.svg" alt="" />
        <img src="../images/icon-instagram.svg" alt="" />
      </div>
      <div class="background-hill-image">
        <img src="../images/pattern-hills.svg" alt="hill" class="hill-image" />
      </div>
    </article>
  </main>
</template>
<script>
export default {
  name: "CounterTimer",
  data() {
    return {
      days: "",
      hours: "",
      minutes: "",
      seconds: "",
      toggleSecondsPage: "",
      toggleMinutesPage: "",
      toggleHoursPage: "",
      toggleDaysPage: "",
      flipSecond: false,
      flipMinutes: false,
      flipHours: false,
      flipDays: false,
    };
  },

  methods: {
    startCounter: function () {
      setInterval(() => {
        this.flipSecond = false;
        if (this.toggleSecondsPage !== this.seconds) {
          this.flipSecond = !this.flipSecond;
          this.toggleSecondsPage = this.seconds;
        }
      }, 500);
      setInterval(() => {
        this.flipMinutes = false;
        if (this.toggleMinutesPage !== this.minutes) {
          this.flipMinutes = !this.flipMinutes;
          this.toggleMinutesPage = this.minutes;
        }
      }, 500);
      setInterval(() => {
        this.flipHours = false;
        if (this.toggleHoursPage !== this.hours) {
          this.flipHours = !this.flipHours;
          this.toggleHoursPage = this.hours;
        }
      }, 500);
      setInterval(() => {
        this.flipDays = false;
        if (this.toggleDaysPage !== this.days) {
          this.flipDays = !this.flipDays;
          this.toggleDaysPage = this.days;
        }
      }, 500);
      setInterval(() => {
        this.seconds = new Date().getSeconds();
      }, 1000);
      setInterval(() => {
        this.minutes = new Date().getMinutes();
      }, 1000);
      setInterval(() => {
        this.hours = new Date().getHours();
      }, 1000);
      setInterval(() => {
        this.days = new Date().getDate();
      }, 1000);
    },
  },

  mounted() {
    const nowTime = new Date();
    this.days = nowTime.getDate();
    this.toggleMinutesPage = nowTime.getDate();
    this.hours = nowTime.getHours();
    this.toggleMinutesPage = nowTime.getHours();
    this.minutes = nowTime.getMinutes();
    this.toggleMinutesPage = nowTime.getMinutes();
    this.seconds = nowTime.getSeconds();
    this.toggleSecondsPage = nowTime.getSeconds();
    this.startCounter();
  },
};
</script>

<style>
* {
  padding: 0px;
  margin: 0px;
  box-sizing: border-box;
}
html {
  background-color: hsl(235, 16%, 14%);
  background-image: url("../images/bg-stars.svg");
}
body {
  font-family: "Red Hat Text", sans-serif;
  font-size: 14px;
  color: hsl(237, 18%, 59%);
  text-transform: uppercase;
  letter-spacing: 0.3rem;
}
.main-component {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
}
.timer-section {
  width: 70%;
  margin-top: -20%;
}
.coming-soon {
  color: hsl(0, 0%, 100%);
  padding: 3rem;
}
.heading-text-article {
  display: flex;
  justify-content: center;
  text-align: center;
  font-size: 1.5rem;
}
/* counter styling starts here */
.counter-article-component {
  display: grid;
  grid-template-columns: repeat(4, 140px);
  gap: 20px;
  justify-content: center;
}

.box-text-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
/* animation start */

.rotating-page-container {
  position: absolute;
  perspective: 1000px;
  height: 4rem;
  width: 8rem;
  z-index: 1;
  font-size: 4rem;
}
.rotating-page {
  position: absolute;
  height: 100%;
  width: 100%;
  /* overflow: hidden; */
  transform-style: preserve-3d;
  transform-origin: center bottom;
}
.flip-page {
  animation: rotation 0.6s ease-in-out 1;
}

@keyframes rotation {
  0% {
    transform: rotateX(-1deg);
  }
  100% {
    transform: rotateX(-181deg);
  }
}
.page {
  position: absolute;
  height: 100%;
  width: 100%;
  backface-visibility: hidden;
  -webkit-backface-visibility: hidden;
  -moz-backface-visibility: hidden;
  display: flex;
  justify-content: center;
  color: hsl(345, 95%, 68%);
  overflow: hidden;
  border-radius: 1rem;
  z-index: 1;
}
.front-page {
  background-color: hsl(235, 31%, 25%);
  /* background-color: red; */
}
.back-page {
  /* background-color: blue; */
  background-color: hsl(236, 32%, 30%);
  transform: rotateX(180deg);
}

.up-box {
  background-color: hsl(235, 31%, 25%);
  height: 4rem;
  width: 8rem;
  border-top-left-radius: 1rem 1rem;
  border-top-right-radius: 1rem 1rem;
  position: relative;
  overflow: hidden;
  color: hsl(345, 95%, 68%);
  font-size: 4rem;
  display: flex;
  justify-content: center;
}
.up-box:before {
  content: "";
  background-color: hsl(235, 16%, 14%);
  position: absolute;
  height: 20px;
  width: 20px;
  top: 52px;
  left: -10px;
  border-radius: 1rem;
  z-index: 2;
}
.up-box:after {
  content: "";
  background-color: hsl(235, 16%, 14%);
  position: absolute;
  height: 20px;
  width: 20px;
  top: 52px;
  left: 118px;
  border-radius: 1rem;
  z-index: 2;
}
.up-numbers {
  position: absolute;
  top: 35%;
}
.down-box {
  background-color: hsl(236, 32%, 30%);
  height: 4rem;
  width: 8rem;
  margin-bottom: 1rem;
  border-bottom-left-radius: 1rem 1rem;
  border-bottom-right-radius: 1rem 1rem;
  position: relative;
  overflow: hidden;
  color: hsl(345, 95%, 68%);
  font-size: 4rem;
  display: flex;
  justify-content: center;
}
.down-box:before {
  content: "";
  background-color: hsl(235, 16%, 14%);
  position: absolute;
  height: 20px;
  width: 20px;
  top: -10px;
  left: -10px;
  border-radius: 1rem;
}
.down-box:after {
  content: "";
  background-color: hsl(235, 16%, 14%);
  position: absolute;
  height: 20px;
  width: 20px;
  top: -10px;
  left: 118px;
  border-radius: 1rem;
}
.down-numbers {
  position: absolute;
  top: -65%;
}
/* background hill image section */
.social-icons {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 2rem;
  position: fixed;
  bottom: 4rem;
  left: 47vw;
}
.hill-image {
  width: 100%;
  position: fixed;
  bottom: 0px;
  left: 0px;
  z-index: -1;
}
@media only screen and (max-width: 500px) {
  body {
    font-size: 8px;
  }
  .timer-section {
    width: 90%;
    margin-top: -20%;
  }
  .heading-text-article {
    font-size: 1rem;
  }
  .counter-article-component {
    display: grid;
    grid-template-columns: repeat(4, 80px);
    gap: 5px;
    justify-content: center;
  }
  .box {
    width: 4rem;
  }
  .rotating-page-container {
    height: 2rem;
    width: 4rem;
    font-size: 2rem;
  }
  .up-box {
    height: 2rem;
    width: 4rem;
    font-size: 2rem;
  }
  .up-box:before {
    height: 10px;
    width: 10px;
    top: 25px;
    left: -5px;
  }
  .up-box:after {
    height: 10px;
    width: 10px;
    top: 25px;
    left: 59px;
  }
  .up-numbers {
    position: absolute;
    top: 35%;
  }
  .down-box {
    height: 2rem;
    width: 4rem;
    font-size: 2rem;
  }
  .down-box:before {
    height: 10px;
    width: 10px;
    top: -5px;
    left: -5px;
  }
  .down-box:after {
    height: 10px;
    width: 10px;
    top: -5px;
    left: 59px;
  }
  .down-numbers {
    position: absolute;
    top: -65%;
  }
  .social-icons {
    left: 35vw;
  }
  .social-icons {
    bottom: 0.1rem;
  }
}
</style>
