<template>
  <div id="scrollContainer" class="content">
      <AgeRestriction/>
      <Header/>
      <FullSizeContent class="snap"/>
      <a class="fullpage_btn" id="arrow" @click="scrollScreen()">
        <div class="arrow left"></div>
        <div class="arrow right"></div>
      </a>
      <div class="text snap" id="baseDesc">
        <h1>Erlesener Geschmack</h1>
      </div>
      <product-select class="snap" style="padding-top: 120px; padding-bottom: 200px;"/>
      <alternating-text class="snap"/>
        <span>
          Einzigartiger intensiver Geschmack aus speziell handausgesuchten Früchten.<br>
          <span class="bold">Seit 1871</span> hergestellt im hauseigenen Destillierungshaus.<br>
          Allgemein steht hier sonst auch ganz viel Text.
        </span>
      <div class="Footer">
        Imperessum
        Kontakt
      </div>
  </div>
</template>

<script>
import AgeRestriction from './components/AgeRestriction.vue'
import FullSizeContent from './components/FullSizeContent.vue'
import ProductSelect from './components/ProductSelect.vue'
import AlternatingText from './components/AlternatingText.vue'
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    FullSizeContent,
    ProductSelect,
    AgeRestriction,
    AlternatingText,
    Header
  },
  methods: {
    scrollScreen() {
      document.getElementById('scrollContainer').scrollBy(0,screen.height);
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  color: #998675;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

body {
  background-color: #1f1f1f;
  height: 100vh;
  overflow: hidden;
}

#app {
  margin: auto;
  max-width: 1920px;
}

#scrollContainer {
  max-width: 1920px;
  overflow-y: scroll;
  height: 100vh;
  scroll-snap-type: y mandatory;
  scroll-behavior: smooth;


  -ms-overflow-style: none;  /* IE and Edge */
  scrollbar-width: none;  /* Firefox */
}

#scrollContainer::-webkit-scrollbar {
  display: none; /* Chrome */
}

#scrollContainer div {
  scroll-snap-stop: always;
}

.snap {
  scroll-snap-align: start;
}


.restricted {
  flex: 1;
  background-color: black;
  z-index: -10;
}

#baseDesc {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.text {
  height: 100vh;
  margin: auto;
}

.text .bold {
  font-weight: bold;
}

.text h1 {
  line-height: 2;
}

.text span {
}

.Footer {
  margin-top: 5%;
}

.arrow.left {
  transform: rotate(-45deg);
  margin-right: -237px;
}

.arrow.right {
  transform: rotate(45deg)
}

.arrow {
  border-radius: 10px;
  width: 5px;
  background-color: white;
  height: 100px;
}

.fullpage_btn {
  width: 100%;
  max-width: 1920px;
  position: absolute;
  background-color: transparent;
  margin-left: auto;
  margin-right: auto;
  display: flex;
  gap: 300px;
  justify-content: center;
  bottom: 0;
}

.fullpage_btn:hover div {
  background-color:rgba(73, 67, 67, 0.716);
}
</style>
