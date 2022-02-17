<template>
    <form>
        <div class="form-group row">
            <label class="col-sm-3 col-form-label">Thickness</label>
            <div class="col-sm-5">
                <incrementor
                    v-model="thickness"
                    unit="px"
                />
            </div>
        </div>
        <div class="form-group row">
            <label class="col-sm-3 col-form-label">Color</label>
            <div class="col-sm-2">
                 <b-form-input type="color" v-model="color" /> 
            </div>
        </div>
        <div class="form-group row">
            <label class="col-sm-3 col-form-label">Alignment</label>
            <div class="col-sm-5">
                <div class="btn-group" role="group">
                    <button type="button" class="btn" :class="alignment === 'left' ? 'btn-secondary' : 'btn-outline-secondary'"
                        @click="alignment = 'left'"
                    >
                        <b-icon
                            icon="text-left"
                        ></b-icon>
                    </button>
                    <button type="button" class="btn" :class="alignment === 'center' ? 'btn-secondary' : 'btn-outline-secondary'"
                        @click="alignment = 'center'"
                    >
                        <b-icon
                            icon="text-center"
                        ></b-icon>
                    </button>
                    <button type="button" class="btn" :class="alignment === 'right' ? 'btn-secondary' : 'btn-outline-secondary'"
                        @click="alignment = 'right'"
                    >
                        <b-icon
                            icon="text-right"
                        ></b-icon>
                    </button>
                </div>
            </div>
        </div>
        <div class="form-group row">
            <label class="col-sm-3 col-form-label">Width</label>
            <div class="col-sm-5">
                <incrementor
                    v-model="width"
                    unit="%"
                />
            </div>
        </div>
        <div class="form-group">
            <label class="col-form-label">Padding</label>
            <div class="row">
                <div class="col-sm-6">
                    <label class="col-form-label">Top</label>
                    <incrementor
                        v-model="padding.top"
                        unit="px"
                    />
                </div>
                <div class="col-sm-6">
                    <label class="col-form-label">Right</label>
                    <incrementor
                        v-model="padding.right"
                        unit="px"
                    />
                </div>
            </div>
            <div class="row">
                <div class="col-sm-6">
                    <label class="col-form-label">Bottom</label>
                    <incrementor
                        v-model="padding.bottom"
                        unit="px"
                    />
                </div>
                <div class="col-sm-6">
                    <label class="col-form-label">Left</label>
                    <incrementor
                        v-model="padding.left"
                        unit="px"
                    />
                </div>
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
			thickness: 0,
            width: 100,
            padding: {
                top: 0,
                right: 0,
                bottom: 0,
                left: 0,
            },
            alignment: 'center',
            color: '',
		}
	},
}
</script>