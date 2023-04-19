<template>
    <button @click="sendData">
        {{ variant }}
        <slot></slot>
    </button>
</template>

<script>
export default {
    props: {
        variant: {
            type: String,
            default: 'success'
        },
    },
    setup(props, { emit }) {

        const sendData = () => {
            emit('update', props.variant);
        }

        return {
            sendData
        }
    }
}
</script>