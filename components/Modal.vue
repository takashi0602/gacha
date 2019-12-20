<template>
  <div>
    <div class="c-modal">
      <div class="c-modal-content">
        <h3 class="c-modal-title">{{ number }}</h3>
        <div class="c-modal-footer">
          <button class="btn btn-danger mb-3" @click="returnCapsule">カプセルを戻す</button>
          <button class="btn btn-primary mb-3" @click="continueGacha">ガチャを続ける</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    number: {
      default: 1
    }
  },
  methods: {
    close() {
      this.$emit('closeModal');
    },
    returnCapsule() {
      this.$emit('returnCapsule');
    },
    continueGacha() {
      this.$emit('continueGacha');
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
  position: absolute;
  top: 42.5%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 150px;
}
.c-modal-footer {
  display: flex;
  flex-wrap: wrap;
  position: absolute;
  width: 100%;
  justify-content: space-around;
  bottom: 30px;
  padding: 0 20px;
}
</style>
