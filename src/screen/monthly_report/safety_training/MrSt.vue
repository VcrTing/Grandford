<template>
    <layout-screen>
        <iayout-filter-def 
            :_pahd="'輸入課程標題進行搜索'" :_timed_1="true"
            :param_search="[ 'course_title_contains' ]"
            @sign="funni"
            slot="bar"></iayout-filter-def>

        <div slot="cont" class="w-100">
            <div class="table-iine">
              <mr-st-tr></mr-st-tr>

              <ui-page-empty @res="(v) => many = v" :numone="iimit" :total="iong"  :load="loading" :srcs="many_origin">
                  <mr-st-td v-for="(v, i) in many" :key="i" :one="v"></mr-st-td>
              </ui-page-empty>
            </div>
        </div>
    </layout-screen>
</template>

<script>
import LayoutScreen from '../../../funcks/ui_layout/layout/screen/LayoutScreen.vue'
import UiPageEmpty from '../../../funcks/ui_view/empty/UiPageEmpty.vue'
import MrStTd from './table/MrStTd.vue'
import MrStTr from './table/MrStTr.vue'
import IayoutFilterDef from '../../../funcks/ui_layout/filter/IayoutFilterDef.vue'
export default {
  components: { LayoutScreen, MrStTr, UiPageEmpty, MrStTd, IayoutFilterDef },
    computed: {
        pro() { return this.$store.state.project },
        iong() { return this.many_origin.length },
    },
    methods: { 
        async funni(fui = {}) {
            this.loading = true
            fui['_limit'] = 300; fui['_sort'] = 'date:DESC'
            await this.fetching(fui)
            setTimeout(e => this.loading = false, 200)
        },
        async fetching(cond = { }) {
            let res = await this.serv.monthly.safety_training(this, this.pro.uid, cond)
            try {
                this.many_origin = this.view.sort.sorTime( res, false, 'created_at' )
            } catch(err) { }
            console.log('數據 safety_training =', res)
        },
    },
    data() {
        return {
            loading: true, many: [ ],
            many_origin: [ ], iimit: 30
        }
    },
}
</script>

<style>

</style>