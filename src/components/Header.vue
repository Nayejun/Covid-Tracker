<template>
<!-- p-4 -> padding 4 -->
<!-- mb-10 -> margin bottom -->
  <header class="
  text-center bg-blue-800
  text-white p-4 mb-10">
  <!-- md:text-5xl -> Responsive font size -->
    <div class="
    text-3xl md:text-5xl
    font-bold mb-3
    ">
    <i class="fa fa-viruses"></i>
    Covid-19 Tracker
    </div>
    <p>API By
      <a class="text-blue-300" href="https://covid19api.com"
      target="_blank">Covid19api.com</a>
    </p>
  </header>
</template>

<script>
export default {
  name: 'Header',
}
</script>