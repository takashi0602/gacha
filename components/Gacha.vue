<template>
  <div class="c-gacha">
    <div class="c-gacha-container">
      <div class="c-gacha-box">
        <div class="c-gacha-capsule c-move-1">
          <div class="c-gacha-capsule-color c-red" />
        </div>
        <div class="c-gacha-capsule c-move-2">
          <div class="c-gacha-capsule-color c-blue" />
        </div>
        <div class="c-gacha-capsule c-move-3">
          <div class="c-gacha-capsule-color c-green" />
        </div>
        <div class="c-gacha-capsule c-move-4">
          <div class="c-gacha-capsule-color c-yellow" />
        </div>
        <div class="c-gacha-capsule c-move-5">
          <div class="c-gacha-capsule-color c-green" />
        </div>
        <div class="c-gacha-capsule c-move-6">
          <div class="c-gacha-capsule-color c-blue" />
        </div>
        <div class="c-gacha-capsule c-move-7">
          <div class="c-gacha-capsule-color c-yellow" />
        </div>
        <div class="c-gacha-capsule c-move-8">
          <div class="c-gacha-capsule-color c-green" />
        </div>
        <div class="c-gacha-capsule c-move-9">
          <div class="c-gacha-capsule-color c-red" />
        </div>
        <div class="c-gacha-capsule c-move-10">
          <div class="c-gacha-capsule-color c-yellow" />
        </div>
        <div class="c-gacha-capsule c-move-11">
          <div class="c-gacha-capsule-color c-green" />
        </div>
        <div class="c-gacha-capsule c-move-12">
          <div class="c-gacha-capsule-color c-red" />
        </div>
        <div class="c-gacha-capsule c-move-13">
          <div class="c-gacha-capsule-color c-blue" />
        </div>
      </div>
      <div class="c-gacha-body">
        <div class="c-gacha-handle">
          <div v-if="startAnimation" class="c-gacha-handle-bar c-rotate-animation" />
          <div v-else class="c-gacha-handle-bar" />
        </div>
        <div class="c-gacha-exit">
          <div v-if="startAnimation" class="c-gacha-capsule c-show-animation">
            <div class="c-gacha-capsule-color" :style="{background: returnColor()}" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    startAnimation: {
      default: false
    }
  },
  data() {
    return {
      colorClass: [
        'red',
        'blue',
        'green',
        'yellow'
      ]
    }
  },
  methods: {
    returnColor() {
      return this.colorClass[Math.floor(Math.random() * 4)];
    }
  }
}
</script>

<style scoped>
.c-red {
  background-color: red;
}
.c-blue {
  background-color: blue;
}
.c-green {
  background-color: green;
}
.c-yellow {
  background-color: yellow;
}

.c-gacha-container {
  position: relative;
}

.c-gacha {
  width: 100%;
  height: 420px;
}

.c-gacha-capsule {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%) rotate(10deg);
  width: 55px;
  height: 55px;
  border-radius: 50%;
  background-color: white;
  border: 1px solid gray;
}
.c-gacha-capsule-color {
  position: absolute;
  top: -1px;
  left: -1px;
  width: 55px;
  height: 27.5px;
  border-radius: 50% / 100% 100% 0 0;
}

.c-gacha-box {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  box-sizing: border-box;
  width: 250px;
  height: 200px;
  border-radius: 40% 40% 20% 20% / 40% 40% 30% 30%;
  background-color: white;
  border: 1px solid gray;
}

.c-gacha-body {
  position: absolute;
  top: 198px;
  left: 50%;
  transform: translateX(-50%);
  box-sizing: border-box;
  width: 175px;
  height: 180px;
  border-radius: 5px;
  background-color: rgba(255, 25, 25, 1);
  border: 1px solid gray;
}

.c-gacha-handle {
  position: absolute;
  top: 10%;
  left: 50%;
  transform: translateX(-50%);
  width: 70px;
  height: 70px;
  border-radius: 50%;
  background-color: rgba(150, 150, 150, 1);
  border: 1px solid gray;
}
.c-gacha-handle-bar {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%) rotate(0);
  width: 60px;
  height: 10px;
  border-radius: 3px;
  background-color: rgba(200, 200, 200, 1);
  border: 1px solid gray;
}

.c-gacha-exit {
  position: absolute;
  bottom: 10px;
  left: 10px;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  background-color: white;
  border: 1px solid gray;
}

.c-move-1 {
  top: 143px;
  left: 22px;
  transform: rotate(30deg);
}
.c-move-2 {
  top: 143px;
  left: 72px;
  transform: rotate(220deg);
}
.c-move-3 {
  top: 143px;
  left: 122px;
  transform: rotate(70deg);
}
.c-move-4 {
  top: 143px;
  left: 172px;
  transform: rotate(130deg);
}
.c-move-5 {
  top: 93px;
  left: 1px;
  transform: rotate(200deg);
}
.c-move-6 {
  top: 93px;
  left: 49px;
  transform: rotate(340deg);
}
.c-move-7 {
  top: 93px;
  left: 99px;
  transform: rotate(70deg);
}
.c-move-8 {
  top: 93px;
  left: 145px;
  transform: rotate(250deg);
}
.c-move-9 {
  top: 93px;
  left: 192px;
  transform: rotate(190deg);
}
.c-move-10 {
  top: 43px;
  left: 22px;
  transform: rotate(330deg);
}
.c-move-11 {
  top: 43px;
  left: 72px;
  transform: rotate(160deg);
}
.c-move-12 {
  top: 43px;
  left: 122px;
  transform: rotate(10deg);
}
.c-move-13 {
  top: 43px;
  left: 172px;
  transform: rotate(70deg);
}

.c-rotate-animation {
  animation: rotate 3s 1;
}
@keyframes rotate {
  0% {
    transform: translate(-50%, -50%) rotate(0);
  }
  40% {
    transform: translate(-50%, -50%) rotate(90deg);
  }
  60% {
    transform: translate(-50%, -50%) rotate(90deg);
  }
  100% {
    transform: translate(-50%, -50%) rotate(180deg);
  }
}

.c-show-animation {
  visibility: hidden;
  animation: show 3.5s 1 forwards;
}
@keyframes show {
  0% {
    visibility: hidden;
  }
  90% {
    visibility: hidden;
  }
  100% {
    visibility: visible;
  }
}
</style>
