<template>
    <form>
        <div class="form-group row">
            <label class="col-sm-3 col-form-label">Height</label>
            <div class="col-sm-5">
                <incrementor
                    v-model="height"
                    unit="px"
                />
            </div>
        </div>
    </form>
</template>

<script>
import Incrementor from '../../custom-ui/Incrementor.vue'

export default {
    components: {
        Incrementor,
    },
    data() {
		return {
			height: 0,
		}
	},
}
</script>