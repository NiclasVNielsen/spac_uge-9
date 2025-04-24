<script setup>
import { ref } from "vue"

const props = defineProps({
  data: Array
})

const keys = ref([])
const itemKeyDisplay = ref([])

let i = 0
for (const key in props.data[0]) {
    i++
    keys.value.push(key)
    itemKeyDisplay.value.push(i < 4 ? true : false)
}



const toggleSearches = () => {
    document.querySelector('.searchFieldsContainer').classList.toggle('on')
}

</script>

<template>

    
<div class="container">
    <div class="col-8 navPadding">
        <div class="container showCheckboxes shadow b">
            <div v-for="(key, index) in keys" :key="keys">
                <input type="checkbox" :id="key + 'show'" v-model="itemKeyDisplay[index]">
                <label :for="key + 'show'">{{ key }}</label>
            </div>
        </div>
        <div class="container border b tableHeading">
            <div>
                <input type="checkbox" id="selectAll">
                <label for="selectAll" class="border a"></label>
            </div>
            <template v-for="(key, index) in keys" :key="keys">
                <p v-if="itemKeyDisplay[index]">
                    {{ key }}
                </p>
            </template>
        </div>
        <ol>

            <li class="shadow b" v-for="(item, index) in props.data" :key="index">
                <div>
                    <input type="checkbox" :id="index + 'item'">
                    <label :for="index + 'item'" class="border a"></label>
                </div>
                <template v-for="(key, index) in keys" :key="index">
                    <div v-if="itemKeyDisplay[index]">
                        {{ item[key] }}
                    </div>
                </template>
            </li>

        </ol>
        <div class="searchPanel">
            <div class="alignment">
                <div class="linkBox" @click="toggleSearches()">
                    Search
                </div>
                <div class="searchFieldsContainer">
                    <div class="container border searchInputs">
                        <label for="">
                            Title
                        </label>
                        <input type="text" placeholder="Title">
                    </div>
                    <div class="container border searchInputs">
                        <label for="">
                            Title2
                        </label>
                        <input type="text" placeholder="Title">
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div class="col-4 shadow l">
        moop
    </div>
    
</div>

</template>

<style lang="sass" scoped>

ol
    list-style: none
    width: 100%
    li
        padding: var(--sameContextGap)
        width: 100%
        display: flex
        border: solid 3px transparent
        align-items: center
        >div
            width: 100%
            margin-right: var(--sameContextGap)
            &:first-of-type
                width: auto
        input
            width: auto
            margin-bottom: 0
            display: none
            &:checked
                + label::after
                    content: "x"
                    font-weight: bold
                    font-size: 1.2em
        label.border.a
            width: 1.5rem
            height: 1.5rem
            padding: 0
            display: flex
            align-items: center
            justify-content: center

.showCheckboxes
    display: flex
    flex-wrap: wrap
    padding: 0
    border: solid 3px transparent
    div
        display: flex
        width: auto
        padding: calc(var(--sameContextGap) / 2) var(--sameContextGap)
        input
            width: auto
            margin: 0
            display: none
            &:checked
                + label
                    color: var(--prim)
        label
            display: flex
            align-items: center

.tableHeading
    display: flex
    flex-wrap: nowrap
    >div
        width: auto
        margin-right: var(--sameContextGap)
    p
        margin-bottom: 0
        padding-right: var(--sameContextGap)
    input
        width: auto
        margin-bottom: 0
        display: none
        &:checked
            + label::after
                content: "x"
                font-weight: bold
                font-size: 1.2em
    label.border.a
        width: 1.5rem
        height: 1.5rem
        padding: 0
        display: flex
        align-items: center
        justify-content: center

.searchInputs
    input
        margin-bottom: 0

.navPadding
    padding-left: 60px

.col-4, .col-8
    min-height: calc(100vh - (var(--sameContextGap) * 2))
    position: relative

.searchPanel
    position: fixed
    z-index: 100
    bottom: 0
    left: 0
    padding: var(--sameContextGap)
    .alignment
        position: relative
        width: 66.666%
        padding-right: var(--sameContextGap)
        padding-left: 60px
        justify-content: flex-end
        display: flex
        .linkBox
            width: auto
        .searchFieldsContainer
            width: calc(100% - (6px + (var(--sameContextGap) * 3.6) + 61px))
            padding-left: 60px
            margin-right: calc(6px + (var(--sameContextGap) * 3.6) + 61px)
            position: absolute
            bottom: 0
            margin-bottom: calc(1 - var(--sameContextGap))
            transform: translateY(calc(100% + var(--sameContextGap)))
            transition: var(--quickTransition)
            background: var(--neutral)
            &.on
                transform: translateY(var(--sameContextGap))
            .searchInputs
                padding-top: 0
                &::first-of-type
                    margin-top: var(--sameContextGap)
                &:last-of-type
                    margin-bottom: -3px
                label
                    border: var(--borderSizeLight) solid var(--prim)
                    border-radius: var(--borderRadius) var(--borderRadius) 0 0
                    border-bottom: 0
                    width: 100%
                    padding: 3px var(--sameContextGap)
                input
                    border-top: 0
                    border-radius: 0 0 var(--borderRadius) var(--borderRadius)
                    
            

</style>