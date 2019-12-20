<template>
  <div>
    <div class="c-modal">
      <div class="c-modal-content">
        <h3 class="c-modal-title">終了しました！</h3>
        <button class="btn btn-primary px-5 c-modal-btn-primary" @click="close">閉じる</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    close() {
      this.$emit('close');
    }
  }
}
</script>

<style scoped>
.c-modal {
  width: 100vw;
  height: 100vh;
  background-color: rgba(100, 100, 100, 0.4);
  position: fixed;
  top: 0;
  left: 0;
}
.c-modal-content {
  width: 50%;
  height: 500px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: white;
  text-align: center;
}
.c-modal-title {
  width: 100%;
  position: absolute;
  top: 42.5%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 50px;
  padding: 0 20px;
}
.c-modal-btn-primary {
  position: absolute;
  bottom: 50px;
  left: 50%;
  transform: translateX(-50%);
}
</style>
