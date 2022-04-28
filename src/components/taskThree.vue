<template>
  <h2>{{ textTask }}</h2>
  <div class="contaner">
    <div class="img-wrapper">
      <img
        v-if="isSurferVisible"
        src="../assets/surfpeak.jpeg"
        alt=""
        :class="imgFilters"
        :style="[changeImgSize, rotateImg]"
      />
      <h4 v-else>Surfer will be back</h4>
    </div>
    <div class="tools">
      <h3>Surfing</h3>
      <div class="btn-effects">
        <button
          type="button"
          @click="isSurferVisible = !isSurferVisible"
          :class="!isSurferVisible ? 'button-active' : ''"
        >
          Hide/Show
        </button>
        <button
          type="button"
          @click="imgFilters.sepia = !imgFilters.sepia"
          :class="imgFilters.sepia ? 'button-active' : ''"
        >
          No colors
        </button>
        <button
          type="button"
          @click="imgFilters.border = !imgFilters.border"
          :class="imgFilters.border ? 'button-active' : ''"
        >
          Border
        </button>
        <button
          type="button"
          @click="imgFilters.shadow = !imgFilters.shadow"
          :class="imgFilters.shadow ? 'button-active' : ''"
        >
          Shadow
        </button>

        <h3>Changing img sizes</h3>
        <div class="btn-effects">
          <label>
            Width:{{ imgSizes.currentWidth }}
            <input
              type="range"
              :value="imgSizes.currentWidth"
              @input="imgSizes.currentWidth = $event.target.value"
              :min="imgSizes.minWidth"
              :max="imgSizes.maxWidth"
            />
          </label>
          <br />
          <label>
            Height:{{ imgSizes.currentHeight }}
            <input
              type="range"
              :value="imgSizes.currentHeight"
              @input="imgSizes.currentHeight = $event.target.value"
              :min="imgSizes.minHeight"
              :max="imgSizes.maxHeight"
            />
          </label>
        </div>
        <h3>Rotate</h3>
        <label>
          Angle:{{ imgRotate.currentAngle }}
          <input
            type="range"
            :value="imgRotate.currentAngle"
            @input="imgRotate.currentAngle = $event.target.value"
            :min="imgRotate.minAngle"
            :max="imgRotate.maxAngle"
          />
        </label>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "taskThree",
  data() {
    return {
      textTask: "Task 3",
      isSurferVisible: true,
      imgFilters: {
        sepia: false,
        border: false,
        shadow: false,
      },
      imgSizes: {
        maxWidth: 640,
        maxHeight: 480,
        currentWidth: 640,
        currentHeight: 480,
      },
      imgRotate: {
        maxAngle: 360,
        minAngle: 0,
        currentAngle: 0,
      },
    };
  },
  computed: {
    changeImgSize() {
      return {
        width: `${this.imgSizes.currentWidth}px`,
        height: `${this.imgSizes.currentHeight}px`,
      };
    },
    rotateImg() {
      return {
        transform: `rotate(${this.imgRotate.currentAngle}deg)`,
      };
    },
  },
};
</script>

<style>
.contaner {
  display: flex;
}

.img-wrapper,
.img-wrapper img {
  width: 640px;
  height: 480px;
  background: lightgray;
}

.img-wrapper .sepia {
  filter: sepia(100%);
}

.img-wrapper .border {
  border: 5px solid black;
}

.img-wrapper .shadow {
  box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
}

.tools {
  margin-left: 35px;
}

.btn-effects button {
  margin-right: 10px;
}

.button-active {
  background: rgb(177, 168, 168);
}
</style>