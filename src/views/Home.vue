<template>
  <div id="home" class="page-wrapper">
    <InvoiceList/>
    <InvoiceCreate/>
    <InvoiceEdit/>
  </div>
</template>

<script>
import ActionBar from "@/components/ActionBar.vue"
import InvoiceList from "@/components/InvoiceList.vue"
import InvoiceCreate from "@/components/InvoiceCreate.vue"
import InvoiceEdit from "@/components/InvoiceEdit.vue"
import DeleteInvoice from "@/components/DeleteInvoice.vue"

export default {
  name: 'Home',
  data(){
    return{
      data: Object,
    }
  },
  components:{
    ActionBar,
    InvoiceList,
    InvoiceCreate,
    InvoiceEdit,
    DeleteInvoice,
  },
  created(){
    this.$store.dispatch('setInvoiceCreate', false)
    this.$store.dispatch('setShowEdit', false)
    this.$store.dispatch('setShowDelete', false)
  },
}
</script>
<style lang="scss" scoped>
@import '@/styles/views/_home.scss';
.page-enter-from,
.page-leave-to{
    opacity: 0;
    transform: translateX(-110%);
}
</style>
