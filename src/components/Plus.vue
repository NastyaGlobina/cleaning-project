<template>
  <div class="plus" @click="show=!show">
    <div v-show="show" class="show-text">
      {{ text }}
      <div class="triangle">
      </div>
    </div>
    <div class="btn-round">
      <svg v-show="!show" width="12" height="12" viewBox="0 0 12 12" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path fill-rule="evenodd" clip-rule="evenodd"
              d="M5 12C5 12.5523 5.44772 13 6 13C6.55228 13 7 12.5523 7 12V7H12C12.5523 7 13 6.55228 13 6C13 5.44772 12.5523 5 12 5H7V0C7 -0.552285 6.55228 -1 6 -1C5.44772 -1 5 -0.552285 5 0V5H0C-0.552285 5 -1 5.44772 -1 6C-1 6.55228 -0.552285 7 0 7H5V12Z"
              fill="white"/>
      </svg>
      <svg v-show="show" width="12" height="12" viewBox="0 0 12 12" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path fill-rule="evenodd" clip-rule="evenodd"
              d="M1.26314 9.74851C0.872619 10.139 0.872619 10.7722 1.26314 11.1627C1.65367 11.5532 2.28683 11.5532 2.67736 11.1627L6.21289 7.62718L9.74842 11.1627C10.1389 11.5532 10.7721 11.5532 11.1626 11.1627C11.5532 10.7722 11.5532 10.139 11.1626 9.74851L7.6271 6.21297L11.1626 2.67744C11.5532 2.28691 11.5532 1.65375 11.1626 1.26322C10.7721 0.8727 10.1389 0.872699 9.74842 1.26322L6.21289 4.79876L2.67736 1.26322C2.28683 0.8727 1.65367 0.8727 1.26314 1.26322C0.872619 1.65375 0.872619 2.28691 1.26314 2.67744L4.79868 6.21297L1.26314 9.74851Z"
              fill="white"/>
      </svg>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false
    }
  },
  props: {
    text: String
  },
}
</script>