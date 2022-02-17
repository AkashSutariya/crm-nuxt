<template>
    <ContentsCore
        title="SECTION"
        :draghandle="draghandle"
        @remove-content="$emit('remove-content')"
        @open-settings="$emit('open-settings')"
    >
        <div class="d-flex">
            <slot name="left"></slot>
            <slot name="right"></slot>
        </div>
    </ContentsCore>
</template>

<script>

export default {
    components: {
    },
    props: [
        'draghandle',
    ],
}
</script>
