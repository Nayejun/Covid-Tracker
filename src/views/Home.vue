<template>
  <div class="home">
    Hello world
  </div>
</template>

<script>
export default {
  name: 'Home',
  components: {},
  data() {

  },
  methods: {
    // 비동기 처리
    async fetchCovidData() {
      const res = await fetch('https://api.covid19api.com/summary')
      const data = await res.json()
      return data;
    }
  },
  async created() {
    const data = this.fetchCovidData()
    console.log(data)
  },
}
</script>
