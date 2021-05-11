<!--  -->
<template>
  <div v-loading="!singers.length" class="aaa">
    <index-list :data="singers" ></index-list>
  </div>
</template>
<script >
import { getSingerList } from '@/service/singer'
import IndexList from '@/components/index-list/index-list'
export default {
  name: 'singer',
  data() {
    return {
      singers: []
    }
  },
  components: { IndexList },
  async created() {
    const result = await getSingerList()
    this.singers = result.singers
  }
}
</script>
