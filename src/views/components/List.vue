<script setup>

</script>

<template>

    
<div class="container">
    <div class="col-8 navPadding">
        <div class="container showCheckboxes shadow  b">
            <div>
                <input type="checkbox" id="title">
                <label for="title">Title</label>
            </div>
            <div>
                <input type="checkbox" id="title2">
                <label for="title2">Title2</label>
            </div>
        </div>
        <div class="container border b">
            Title
        </div>
        <ol>
            <li class="shadow b">
                1
            </li>
            <li class="shadow b">
                2
            </li>
        </ol>
        <div class="searchPanel">
            <div class="alignment">
                <div class="linkBox">
                    Search
                </div>
                <div class="searchFieldsContainer">
                    <div class="container border searchInputs">
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

.showCheckboxes
    display: flex
    flex-wrap: wrap
    padding: 0
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
        width: 66.666%
        padding-right: var(--sameContextGap)
        padding-left: 60px
        justify-content: flex-end
        display: flex
        .linkBox
            width: auto
        .searchFieldsContainer
            position: absolute
            bottom: -100%

</style>