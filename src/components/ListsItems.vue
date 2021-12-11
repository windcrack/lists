<template lang="pug">
    ul.items(v-show="visible")
        li(v-for="(item, i) in lists" :key="i" ).item 
            input(type="checkbox" :checked="item.chek" @click="open(i)").checkbox
            label.item__text item {{i + 1}}
            input(type="text" :value="item.count").item__count
            input(type="color" v-model="item.color").item__color
</template>
<script>
export default {
    props: ['visible' ,'lists', 'open'],
}
</script>
<style lang="sass">
    
</style>