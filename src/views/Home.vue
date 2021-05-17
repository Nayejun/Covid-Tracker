<template>
<!-- 조건부 렌더링 -->
  <main v-if = "!loding">
    <DataTitle :dataDate="dataDate" :text="title" />
    <DataBoxes :stats="stats" />

  </main>

  <main class="flex flex-col align-center justify-center text-center" v-else>
    <div class="text-gray-500 text-3xl mt-10 mb-6">
        Fetching Data
    </div>
    <img :src="lodingImage" class="w-24 m-auto">
  </main>
</template>

<script>
import DataTitle from '@/components/DataTitle';
import DataBoxes from '@/components/DataBoxes';

export default {
  name: 'Home',
  components: {
    DataTitle,
    DataBoxes
  },
  data() {
    return {
      loding: true,
      title: 'Global',
      dataDate: '',
      status: [],
      countries: [],
      lodingImage: require('../assets/hourglass.gif')
    }
  },
  methods: {
    // 비동기 async 사용
    async fetchCovidData() {
      const res = await fetch('https://api.covid19api.com/summary')
      const data = await res.json()
      return data;
    }
  },
  async created() {
    const data = this.fetchCovidData()

    // API에서 들어오는 Date data를 할당
    this.dataDate = data.Date
    //글로벌 데이터를 통계에 할당
    this.stats = data.Global
    //국가별 데이터
    this.countries = data.Countries
    // 데이터 가져올 때 로딩 이미지 표시
    this.loding = false
  },
}
</script>
