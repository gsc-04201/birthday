<template>
  <div id="app">
    <div class="btnbox">
      <button @click="openModal">OPEN</button>
    </div>


    <div id="overlay" v-if="show">
      <div class="vue_radio">
        <div class="tabs">
          <input type="radio" id="tab1" value="1" v-model="isActive" />
          <label for="tab1">タブメニュー1</label>
          <input type="radio" id="tab2" value="2" v-model="isActive" />
          <label for="tab2">タブメニュー2</label>
          <input type="radio" id="tab3" value="3" v-model="isActive" />
          <label for="tab3">タブメニュー3</label>
        </div>
        <ul class="contents">
          <li v-if="isActive === '1'"><img src="./assets/S__13795340.jpg" alt=""><span class="text">こんちゃ〜<br> あたいはマリーゆうねん</span></li>
          <li v-else-if="isActive === '2'"><img src="./assets/S__13795337.jpg" alt=""><span class="text">今日はなぁ〜<br> あたいの誕生日やねん。</span></li>
          <li v-else-if="isActive === '3'"><img src="./assets/S__13795341.jpg" alt=""><span class="text">マジで卍<br> ハッピーバースデイ‼️</span></li>
        </ul>

    </div>
      <div id="content">
        <p>Happy Birthday!! Maryyy</p>
        <p>My best friend! Maryyyy</p>
        <p>I'm glad to see you </p>
        <p>I will continue to be friends</p>
        <p>I pray for your health</p>
        <p>have nice yearrr!!!!!!</p>
        <button @click="closeModal">CLOSE</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isActive: "1",
      show: false
    };
  },
  methods: {
    openModal() {
      this.show = true;
    },
    closeModal() {
      this.show = false;
    }
  }
};
</script>
<style>
#app {
  margin: 0 20%;
}
.tabs label {
  padding: 5px 75px;
  cursor: pointer;
}
.tabs :checked + label {
  margin: 0 auto;
  background-color: #000;
  color: #fff;
}
input {
  display: none;
}
ul {
  margin: 0;
  padding: 0;
}
li {
  /* margin: 0 auto; */
  list-style: none;
  width: 800px;
  padding: 20px;
  border: 1px solid #ccc;
  display: flex;

}

.text {
  /* margin:0 60px; */
  padding: 20px 50px;
  writing-mode: vertical-rl;
  font-size: 50px;

}
img {
  /* margin: 0 auto; */
  width: 500px;
}

.btnbox {
  text-align: center;
}

#overlay {
  z-index: 1;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
}
#content {
  text-align: center;
  z-index: 2;
  width: 30%;
  padding: 10px;
  background: #fff;
}

p {
  border-bottom: orange 2px solid;
}

</style>