<template>
    <div class="bar1">
      <PageNavbar/>
    </div>
</template>

<script>
import PageNavbar from '@/components/PageNavbar.vue'

export default {
  name: 'PageHeader',
  components: {
    PageNavbar
  }
}
</script>

<style>
.header-container {
  display: flex;
}

.bar1 {
  flex: 1;
}

.bar2 {
  flex: 4;
}
</style>
