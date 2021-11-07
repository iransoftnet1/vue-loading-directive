<template>
  <div :class="['el-loading-spinner',scaleClass]">
    <svg class="circular" viewBox="25 25 50 50">
      <circle class="path" cx="50" cy="50" r="20" fill="none"/>
    </svg>
  </div>
</template>

<script>
export default {
  name: 'spinner',
  props: {
    scaleClass: {
      type: String
    }
  }
}
</script>

<style>
.el-loading-spinner {
  margin-top: 0 !important;
  -webkit-transform: translateY(-50%);
  transform: translateY(-50%);
}

.el-loading-spinner {
  top: 50%;
  margin-top: -21px;
  width: 100%;
  text-align: center;
  position: absolute;
}

.el-loading-spinner .circular {
  vertical-align: middle;
}

.el-loading-spinner .circular {
  height: 42px;
  width: 42px;
  -webkit-animation: loading-rotate 2s linear infinite;
  animation: loading-rotate 2s linear infinite;
}

.el-loading-spinner {
  text-align: center;
}

@keyframes loading-rotate {
  100% {
    -webkit-transform: rotate(360deg);
    transform: rotate(360deg);
  }
}

@keyframes loading-dash {
  0% {
    stroke-dasharray: 1, 200;
    stroke-dashoffset: 0;
  }

  50% {
    stroke-dasharray: 90, 150;
    stroke-dashoffset: -40px;
  }

  100% {
    stroke-dasharray: 90, 150;
    stroke-dashoffset: -120px;
  }
}

.el-loading-spinner .path {
  -webkit-animation: loading-dash 1.5s ease-in-out infinite;
  animation: loading-dash 1.5s ease-in-out infinite;
  stroke-dasharray: 90, 150;
  stroke-dashoffset: 0;
  stroke-width: 4;
  /*stroke-width: 2;*/
  /*stroke: #8e7bea;*/
  stroke: #52d523;
  stroke-linecap: round;
}

.el-loading-spinner .circular {
  vertical-align: middle;
}
</style>
