<template>
  <div class="container p-5">
    <h1 class="c-title text-center mb-5">ITC忘年会~プレゼント交換~</h1>

    <div v-if="!started">
      <div class="mb-5">
        <p>人数を入力してね！</p>
        <div class="d-flex align-items-end">
          <input type="number" class="form-control w-25 mr-3" v-model="peoples" />
          <div>人</div>
        </div>
        <p v-if="notPeoples" class="text-danger">1人以上入力してください。</p>
      </div>
      <div class="text-center">
        <button type="button" class="btn btn-primary px-5 py-2" @click="start">スタート</button>
      </div>
    </div>

    <div v-if="started">
      <div>残りカプセル：{{gachaList.length}}個</div>
      <Gacha :startAnimation="startAnimation" />
      <div class="text-center">
        <button type="button" class="btn btn-primary px-5 py-2" @click="turn">回す</button>
      </div>
    </div>

    <finish-modal
      v-if="finished"
      @close="closeFinishModal"
    />

    <modal
      v-if="showModal"
      :number="hitPeopleNumber"
      @returnCapsule="returnCapsule"
      @continueGacha="continueGacha"
    />

  </div>
</template>

<script>
import Gacha from "~/components/Gacha"
import Modal from "~/components/Modal"
import FinishModal from "~/components/FinishModal"

export default {
  components: {
    Gacha,
    Modal,
    FinishModal
  },
  data() {
    return {
      peoples: 1,
      gachaList: [],
      notPeoples: false,
      started: false,
      finished: false,
      hitPeopleNumber: 0,
      showModal: false,
      randomIndex: 0,
      startAnimation: false
    }
  },
  methods: {
    start() {
      this.notPeoples = false;
      if (this.peoples <= 0) {
        this.notPeoples = true;
        return;
      }
      for (let i = 1; i <= this.peoples; i++) this.gachaList.push(i);
      this.started = true;
    },
    turn() {
      this.randomIndex = Math.floor(Math.random() * this.gachaList.length);
      this.hitPeopleNumber = this.gachaList[this.randomIndex];
      this.startAnimation = true;
      setTimeout(this.openModal, 4000);
    },
    openModal() {
      this.showModal = true;
    },
    finish() {
      this.finished = true;
    },
    returnCapsule() {
      this.startAnimation = false;
      this.showModal = false;
    },
    continueGacha() {
      this.gachaList.splice(this.randomIndex, 1);
      this.startAnimation = false;
      this.showModal = false;
      if (this.gachaList.length === 0) this.finish();
    },
    closeFinishModal() {
      this.started = false;
      this.finished = false;
    }
  }
}
</script>

<style scoped>
.c-title {
  font-size: 64px;
}
</style>
