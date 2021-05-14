<template>
<Header />
<div class="container">
  <router-view />
</div>
</template>

// 다른 페이지나 뷰를 보고 모든 페이지에 가져와야 하는 새로운 경로를 추가.
// 그래서 그것을 메인으로 추가 -> 스크립트

<script>
import Header from '@/components/Header'

//기본 개체, 구성요소
export default {
  components: {
    //여기에 Header를 정의
    Header
  }
}
</script>
