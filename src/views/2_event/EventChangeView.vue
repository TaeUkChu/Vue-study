<template>
  <div>
    <select name="" id="" @change="changeCity($event)" v-model="selectedCity">
      <option value="">==도시선택==</option>
      <option
        :value="city.cityCode"
        :key="city.cityCode"
        v-for="city in cityList"
      >
        {{ city.title }}
      </option>
    </select>
    <select name="" id="">
      <option
        :value="dong.dongCode"
        :key="dong.dongCode"
        v-for="dong in selectedDongList"
      >
        {{ dong.dongtitle }}
      </option>
    </select>
    <select name="" id="">
      <option
        :value="dong.dongCode"
        :key="dong.dongCode"
        v-for="dong in dongList.filter(
          (dong) => dong.cityCode === selectedCity
        )"
      >
        {{ dong.dongtitle }}
      </option>
    </select>
  </div>
</template>
<script>
export default {
  components: {},
  data() {
    return {
      selectedCity: '',
      cityList: [
        { cityCode: '02', title: '서울' },
        { cityCode: '051', title: '부산' },
        { cityCode: '064', title: '제주' }
      ],
      dongList: [
        { cityCode: '02', dongCode: '1', dongtitle: '서울 1동' },
        { cityCode: '02', dongCode: '2', dongtitle: '서울 2동' },
        { cityCode: '02', dongCode: '3', dongtitle: '서울 3동' },
        { cityCode: '02', dongCode: '4', dongtitle: '서울 4동' },
        { cityCode: '051', dongCode: '1', dongtitle: '부산 1동' },
        { cityCode: '051', dongCode: '2', dongtitle: '부산 2동' },
        { cityCode: '051', dongCode: '3', dongtitle: '부산 3동' },
        { cityCode: '064', dongCode: '1', dongtitle: '제주 1동' },
        { cityCode: '064', dongCode: '2', dongtitle: '제주 2동' }
      ],
      selectedDongList: []
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {
    changeCity(event) {
      console.log(event.target.tagName)
      this.selectedDongList = this.dongList.filter(
        (ho) => ho.cityCode === this.selectedCity
      )
    }
  }
}
</script>
