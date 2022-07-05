<template lang="pug">
    .cheblox-body(@click="changerHandler")
        i.fas(:class="`fa-chevron-${visible ? 'down' : 'right'}`")
        input(type="checkbox").for-label#main
        label(for="main" @click="changerHandler")
        span List 1
</template>
<script>
export default {
    props: ['changerHandler', 'visible'],
}
</script>
<style lang="sass">
    
</style>