<template lang="pug">
    .lists-body
        CheckBox(:changerHandler="changerHandler" :visible="visible")
        ListsItems(:visible="visible" :lists="lists" :open="open")
</template>
<script>
import CheckBox from './Checkbox.vue'
import ListsItems from './ListsItems.vue'
export default {
    props: ['lists', 'changerHandler', 'visible'],
    components: {
		CheckBox, ListsItems
	},
    
    methods: {
        open(i){
            let change = this.lists;
            change[i].chek = !change[i].chek
        },
    },
}
</script>
<style lang="sass">
    .lists-body
        width: 502px
        padding: 10px 20px
        border: solid 1px #000
        
    .cheblox-body
        flex-basis: 100%
        display: flex
        align-items: center
        cursor: pointer

    .for-label
        position: absolute
        z-index: -1
        opacity: 0
        cursor: pointer
        &+label
            display: inline-flex
            align-items: center
            user-select: none
            &::before
                content: ''
                display: inline-block
                width: 25px
                height: 25px
                flex-shrink: 0
                flex-grow: 0
                border: 1px solid #000
                border-radius: 0.3rem
                margin: 0 0.75rem
        &:checked
            &+label
                &::before
                    content: '■'

    .checkbox
        border: none
        width: 20px
        height: 30px
        margin-right: 12px

    .items
        width: 400px
        margin-left: 60px
        margin-bottom: 12px
    .item
        display: flex
        align-items: center
        &__text
            margin-right: auto
        &__count
            width: 20px
            height: 20px
            border: none
            margin-right: 6px
        &__color
            width: 25px
            height: 25px
            border: none
            background-color: transparent
</style>