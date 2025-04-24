<script setup>
import { ref } from "vue"

const itemKeyDisplay = ref([true, true])

const toggleSearches = () => {
    document.querySelector('.searchFieldsContainer').classList.toggle('on')
}

</script>

<template>

    
<div class="container">
    <div class="col-8 navPadding">
        <div class="container showCheckboxes shadow b">
            <div>
                <input type="checkbox" id="title" v-model="itemKeyDisplay[0]">
                <label for="title">Title</label>
            </div>
            <div>
                <input type="checkbox" id="title2" v-model="itemKeyDisplay[1]">
                <label for="title2">Title2</label>
            </div>
        </div>
        <div class="container border b tableHeading">
            <p v-if="itemKeyDisplay[0]">
                Title
            </p>
            <p v-if="itemKeyDisplay[1]">
                Title 2
            </p>
        </div>
        <ol>
            <li class="shadow b">
                <input type="checkbox" id="t1">
                <label for="t1" class="border a"></label>
                1
            </li>
            <li class="shadow b">
                <input type="checkbox" id="t2">
                <label for="t2" class="border a"></label>
                2
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
    p
        margin-bottom: 0
        padding-right: var(--sameContextGap)

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
            transform: translateY(100%)
            transition: var(--quickTransition)
            background: var(--neutral)
            &.on
                transform: translateY(0%)
            .searchInputs
                &:last-of-type
                    padding-bottom: 0
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