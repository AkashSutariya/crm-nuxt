<template>
    <ContentsCore
        title="DIVIDER"
        :draghandle="draghandle"
        @remove-content="$emit('remove-content')"
        @open-settings="$emit('open-settings')"
    >
        <hr class="my-0 bg-dark p-1" />
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
