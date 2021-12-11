<template lang="pug">
    .lists-body
        h2.title List 1
        .color-out
            ul.color-out__lists(v-for="(item, i) in lists" :key="i")
                li.color-out__list(v-if="item.chek")
                    input(type="color", v-model="item.color").item__color
</template>
<script>
export default {
    props: ['lists'],
}
</script>
<style lang="sass">
    .title
        font: 16px sans-serif
        text-align: left
    .color-out
        display: flex
        &__lists
            list-style: none
</style>