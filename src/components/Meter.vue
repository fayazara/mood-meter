<template>
  <div class="pt-20">
    <h1 class="text-3xl font-bold text-gray-600 text-center">{{ msg }}</h1>
    <div class="my-8">
      <v-transition enter-active-class="animated fadeIn" leave-active-class="animated fadeOut" mode="out-in">
        <img :key="mood.id" :src="mood.image" class="h-56 w-56 mx-auto" />
      </v-transition>
    </div>
    <div class="h-32 flex items-center justify-center">
      <p class="my-auto text-center text-gray-700 text-3xl">{{ mood.label }}</p>
    </div>
    <range-slider
      class="slider my-4" 
      min="0"
      max="60"
      step="10"
      v-model="sliderValue"
    >
    </range-slider>
  </div>
</template>
<script>
import RangeSlider from 'vue-range-slider';
// you probably need to import built-in style
import 'vue-range-slider/dist/vue-range-slider.css';
export default {
  props: ['msg'],
  data() {
    return {
      sliderValue: 0
    };
  },
  computed: {
    mood() {
      if (this.sliderValue == 10) {
        return {
          id: 1,
          label: 'Tired',
          image: require(`../assets/images/tired.svg`)
        };
      } else if (this.sliderValue == 20) {
        return {
          id: 2,
          label: 'Yeh Ho kya rha hai mere saath!',
          image: require(`../assets/images/anxious.svg`)
        };
      } else if (this.sliderValue == 30) {
        return {
          id: 3,
          label: 'Bhai Maaro Muje!',
          image: require(`../assets/images/sad.svg`)
        };
      } else if (this.sliderValue == 40) {
        return {
          id: 4,
          label: 'Ankh Dikhata hai madarjaat!',
          image: require(`../assets/images/angry.svg`)
        };
      } else if (this.sliderValue == 50) {
        return {
          id: 5,
          label: 'Happy',
          image: require(`../assets/images/happy.svg`)
        };
      } else if (this.sliderValue == 60) {
        return {
          id: 6,
          label: 'Do you smoke beer? No I drink weed!',
          image: require(`../assets/images/bhand.svg`)
        };
      } else {
        return {
          id: 0,
          label: null,
          image: require(`../assets/images/thinking.svg`)
        };
      }
    }
  },
  components: {
    RangeSlider
  }
};
</script>

<style>
.slider {
  width: 100%;
}

.range-slider-knob {
  -webkit-box-shadow: 0 15px 30px 0 rgba(0, 0, 0, 0.11),
    0 5px 15px 0 rgba(0, 0, 0, 0.08);
  background: #f4b350;
  border: 2px solid #e76e3c;
  box-shadow: 0 15px 30px 0 rgba(0, 0, 0, 0.11),
    0 5px 15px 0 rgba(0, 0, 0, 0.08);
  height: 30px;
  width: 30px;
}
.range-slider-rail {
  background: #f4b350;
}

.range-slider-fill {
  background: #e76e3c;
}
</style>
