<template>
  <div v-if="!isAdult" id="age-restriction">
    <div class="popup">
      <img class="HeaderImg" src="./../assets/Logo.png">
      <div>
      <h1>Please verify your age.</h1>
      </div>
      <select id="years" name="years" @change="isAdult = true">
        <option style="display: none"  disabled selected value>Enter Year of Birth</option>
      </select>
    </div>
  </div>
</template>

<script>
/* eslint-disable */

export default {
  name: 'AgeRestriction',
  data() {
    return {
      isAdult: false,
    }
  },
  mounted() {
    var min = 18,
    max = 150,
    select = document.getElementById('years');

    const currentYear = new Date().getFullYear()

    for (var i = min; i<=max; i++){
        var opt = document.createElement('option');
        opt.value = new Date().getFullYear() - i;
        opt.innerHTML = new Date().getFullYear() - i;
        select.appendChild(opt);
    }
  },
  methods: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#age-restriction {
  max-width: 1920px;
  height: 100%;
  position: fixed;
  width: 100%;
  background-color: rgba(0, 0, 0, 0.312);
  z-index: 11;
  backdrop-filter: blur(10px);
  display: flex;
  justify-content: center;
  align-items: center;
}

#age-restriction .popup {
  height: 350px;
  width: 600px;
  background-color: #212121;
  border-radius: 30px;
  border: 3px solid #998675;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
}

#years {
  font-size: 15px;
  border-radius: 15px;
  background-color: #212121;
  appearance: none;
  padding: 1px;
  padding-left: 10px;
  padding-right: 10px;
}

#years::-webkit-scrollbar {
  width: 14px;
  height: 14px;
}

#years::-webkit-scrollbar-track {
  border: none;
  background-color: #212121;
}

#years::-webkit-scrollbar-thumb {
  background-color: #998675;
  border: none;
  border-radius: 5px;
}

.popup img {
  display: inline-flex
}

img {
  height: 70px;
}

.popup h1 {
  height: 70px;
  padding-top: 20px;
}

#btns {
  display: inline-flex;
  gap: 200px;
}

#btns div {
  height: 50px;
  width: 100px;
  border: 1px solid #998675;
  border-radius: 10px;
  text-align: center;
  margin-top: 10px;
}
</style>
