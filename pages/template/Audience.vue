<template>
    <div class="container-fluid">
        <ContentsNavs />
        <form class="mt-5 mx-auto audience">
            <div class="form-group">
                <label for="sendTo">Send To 
                    <sup class="text-danger">*</sup>
                </label>
                <div class="input-group">
                    <input type="text" 
                        class="form-control custom-input" 
                        id="sendTo"
                        placeholder="Select recipients"
                    />
                    <div class="input-group-append">
                        <span class="input-group-text custom-input-append">
                            <b-icon
                                icon="info-circle"
                            ></b-icon>
                        </span>
                    </div>
                </div>
            </div>
            <div class="form-group row">
                <label for="excludeRecipients" class="col-8">
                    Exclude specific recipients
                </label>
                <vue-toggles
                    class="offset-2"
                    width="55"
                    checkedText="On"
                    uncheckedText="Off"
                    checkedBg="#6db6f2"
                    :value="excludeRecipients"
                    @click="excludeRecipients = !excludeRecipients"
                />
            </div>
            <div v-show="excludeRecipients" class="form-group">
                <label for="exclude">Exclude</label>
                <div class="input-group">
                    <input type="text" 
                        class="form-control custom-input" 
                        id="exclude"
                        placeholder="Select recipients"
                    />
                    <div class="input-group-append">
                        <span class="input-group-text custom-input-append">
                            <b-icon
                                icon="info-circle"
                            ></b-icon>
                        </span>
                    </div>
                </div>
            </div>
            <div class="form-group">
                <label for="unsubscribeGroup">Unsubscribe Group
                    <sup class="text-danger">*</sup>
                </label>
                 <select class="form-control" id="unsubscribeGroup">
                    <option>select an unsubscribe group</option>
                </select>
            </div>
        </form>
    </div>
</template>

<script>
import VueToggles from 'vue-toggles';

export default {
    components: {
        VueToggles,
    },
    data() {
        return {
            excludeRecipients: false,
        }
    }
}
</script>