<template>
	<vuejs-datepicker
		:disabled="dis"
		:minimum-view="'day'"
		:maximum-view="'month'"

		:format="'dd / MM / yyyy'"
		:placeholder="pahd"
	    v-if="timed" :value="timed" @selected="result"></vuejs-datepicker>
</template>
<script>
import moment from 'moment'
import VuejsDatepicker from 'vuejs-datepicker'
	export default {
		name: 'app',
		props: {
			dis: Boolean,
			timed: {
				type: String,
				default: () => moment(new Date()).format('YYYY-MM-DD')
			},
            pahd: {
                type: String,
                default: '請選擇日期'
            }
		},
		components: { VuejsDatepicker },
		mounted() {
		},
		methods: {
			setShowDate(d) { this.showDate = d },
			result(v) {
				this.$emit('result', moment(v).format('YYYY-MM-DD'))
			}
		}
	}
</script>
