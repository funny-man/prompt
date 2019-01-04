<template>
  <div class="prompt" v-show="showFlag" @click.stop="cancel">
    <div class="prompt-wrapper" @click.stop>
      <div class="prompt-content">
        <p class="text">{{text}}</p>
        <input ref="input" type="text" name="" id="">
        <div class="operate">
          <div @click="cancel" class="operate-btn left">{{cancelBtnText}}</div>
          <div @click="confirm" class="operate-btn">{{confirmBtnText}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
export default {
  props: {
    text: {
      type: String,
      default: '这是提示内容'
    },
    confirmBtnText: {
      type: String,
      default: '确定'
    },
    cancelBtnText: {
      type: String,
      default: '取消'
    }
  },
  data() {
    return {
      showFlag: false
    }
  },
  methods: {
    show() {
      this.showFlag = true
    },
    hide() {
      this.showFlag = false
    },
    cancel() {
      this.hide()
      this.$emit('cancel')
    },
    confirm() {
      this.hide()
      // eslint-disable-next-line
      console.log(this.$refs.input.value);
      this.$emit('confirm')
    }
  }
}
</script>

<style scoped>
  .prompt {
    position: fixed;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    z-index: 998;
    background-color: rgba(12, 22, 36, 0.9);
  }
  .prompt-wrapper {
    background-color: #fff;
  }
</style>
