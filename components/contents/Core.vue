<template>
    <div class="card">
        <div class="card-header d-flex justify-content-between">
            <span>
                <b-icon
                    v-if="draghandle"
                    icon="arrows-move"
                    class="handle mr-1"
                    role="button"
                ></b-icon>
                {{ title }}
            </span>
            <div class="d-flex">
                <b-icon
                    icon="code"
                    class="mx-1"
                ></b-icon>
                <b-icon
                    role="button"
                    icon="back"
                    class="mx-1"
                    @click="$emit('open-settings')"
                ></b-icon>
                <b-icon
                    role="button"
                    icon="trash"
                    class="mx-1"
                    @click="$emit('remove-content')"
                ></b-icon>
            </div>
        </div>
        <div class="card-body text-center">
            <slot></slot>
        </div>
    </div>
</template>

<script>
export default {
    props: [
        'title',
        'draghandle',
    ],
}
</script>