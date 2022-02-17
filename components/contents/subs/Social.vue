<template>
    <ContentsCore
        title="SOCIAL"
        :draghandle="draghandle"
        @remove-content="$emit('remove-content')"
        @open-settings="$emit('open-settings')"
    >
        <b-icon
            v-for="(social) in socials"
            :key="social.icon"
            :icon="social.icon"
            font-scale="1.5"
            class="mx-2"
        ></b-icon>
    </ContentsCore>
</template>

<script>

export default {
    components: {
    },
    props: [
        'draghandle',
    ],
    data() {
		return {
			socials: [
                {
                    icon: 'facebook',
                },
                {
                    icon: 'twitter',
                },
                {
                    icon: 'youtube',
                },
                {
                    icon: 'linkedin',
                },
                {
                    icon: 'instagram',
                },
            ],
		}
	},
}
</script>
