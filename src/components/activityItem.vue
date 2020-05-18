<template>
  <div>
    <activityItemUpdate v-if="isUpdateActive"
                        :activity="activity"
                        :categories="categories"
                        @toggleUpdate="changeUpdateState" />
    <activityItemDetail v-else
                        :activity="activity"
                        :categories="categories"
                        @toggleUpdate="changeUpdateState" />
  </div>
</template>

<script>
import activityItemDetail from "./activityItemDetail"
import activityItemUpdate from "./activityItemUpdate"
export default {
   components: {
     activityItemDetail, 
     activityItemUpdate
   },
   props: {
     activity: {
       type: Object,
       required: true
     },
     categories: {
       type: Object,
       required: true
     }
   },
   data() {
     return {
       isUpdateActive: false
     }
   },
   methods: {
     changeUpdateState(isUpdate) {
       this.isUpdateActive = isUpdate
     }
   }
}
</script>

<style scoped>

</style>