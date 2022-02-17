<template>
    <div class="container-fluid">
        <ContentsNavs />
        <div class="row">
            <div class="col-6 offset-3">
                <div class="text-center">
                    <h3>Schedule Campaign</h3>
                    <h5 class="text-secondary">
                        Send your campaign now or schedule it in advance
                    </h5>
                </div>
                <div class="mt-3">
                    <div class="form-check">
                        <input class="form-check-input" type="radio" id="sendItNow" :value="true" v-model="sendItNow">
                        <label class="form-check-label font-weight-bold" for="sendItNow">
                            Send it now
                        </label>
                    </div>
                    <div class="form-check">
                        <input class="form-check-input" type="radio" id="sendItLater" :value="false" v-model="sendItNow">
                        <label class="form-check-label font-weight-bold" for="sendItLater">
                            Schedule for a specific time
                        </label>
                    </div>
                </div>
                <form v-show="!sendItNow" class="mt-3">
                    <div class="form-row">
                        <div class="form-group col-4">
                            <label for="date">Date</label>
                            <b-form-datepicker id="date" v-model="date" class="mb-2"
                                :date-format-options="{ year: 'numeric', month: 'numeric', day: 'numeric', weekday: 'long' }"
                            >
                            </b-form-datepicker>
                        </div>
                        <div class="form-group col-5">
                            <label for="inputPassword4">Time (Sydney GMT+11:00)</label>
                            <form>
                                <div class="form-row">
                                    <div class="col-3">
                                        <select v-model="hour" class="form-control">
                                            <option v-for="n in 24" :key="n">{{ n - 1 }}</option>
                                        </select>
                                    </div>
                                    <div class="col-3">
                                        <select v-model="minute" class="form-control">
                                            <option v-for="n in 12" :key="n">{{ (n - 1) * 5 }}</option>
                                        </select>
                                    </div>
                                </div>
                            </form>
                        </div>
                    </div>
                </form>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    components: {
    },
    data() {
        return {
            date: '',
            hour: '0',
            minute: '0',
            sendItNow: true,
        }
    }
}
</script>