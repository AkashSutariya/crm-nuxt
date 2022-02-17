<template>
    <ContentsCore
        title="TEXT"
        :draghandle="draghandle"
        @remove-content="$emit('remove-content')"
        @open-settings="$emit('open-settings')"
    >
        Lorem Ipsum is simply dummy text of the printing and typesetting industry. 
        Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
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
