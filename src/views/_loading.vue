<template>
  <transition name="el-loading-fade" @after-leave="handleAfterLeave">
    <div
      v-show="visible"
      class="el-loading-mask"
      :style="{ backgroundColor: background || '' }"
      :class="[customClass, { 'is-fullscreen': fullscreen }]"
    >
      <packman
        v-if="type === 'packman'"
        v-bind="attr"
      />
      <spinner
        v-else-if="type === 'spinner'"
        v-bind="attr"/>
      <div v-else>
        loading ...
      </div>
      <p v-if="text" class="el-loading-text">{{ text }}</p>
    </div>
  </transition>
</template>

<script>
import packman from './packman'
import spinner from './spinner'

export default {
  components: {
    packman,
    spinner
  },
  data () {
    return {
      text: null,
      background: null,
      fullscreen: true,
      visible: false,
      customClass: '',
      type: null,
      size: null
    }
  },
  computed: {
    attr () {
      return {
        ...this.$data,
        scaleClass: this.scaleClass
      }
    },
    scaleClass () {
      return this.size
        ? 'el-loading-scale-' + this.size
        : ''
    }
  },
  methods: {
    handleAfterLeave () {
      this.$emit('after-leave')
    },
    setText (text) {
      this.text = text
    }
  }
}
</script>
<style lang="scss">
@for $i from 1 through 15 {
  .el-loading-scale-#{$i} {
    transform: scale($i / 10);
  }
}
</style>

<style>
.el-loading-parent--relative {
  position: relative !important;
}

.el-loading-mask {
  position: absolute;
  z-index: 2000;
  /*background-color: rgba(255, 255, 255, 0.9);*/
  background-color: rgba(74, 74, 74, 0.9);
  margin: 0;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  -webkit-transition: opacity 0.3s;
  transition: opacity 0.3s;
}

</style>
