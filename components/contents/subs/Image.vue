<template>
    <ContentsCore
        title="IMAGE"
        :draghandle="draghandle"
        @remove-content="$emit('remove-content')"
        @open-settings="$emit('open-settings')"
    >
        <b-icon
            icon="card-image"
        ></b-icon>
        Add Image
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
