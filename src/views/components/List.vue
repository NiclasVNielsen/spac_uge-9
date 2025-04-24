<script setup>

</script>

<template>

<div class="container">
    <div class="col-8">
        <ol>
            <li class="shadow b">
                1
            </li>
            <li class="shadow b">
                2
            </li>
        </ol>
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

.col-8
    padding-left: 60px

.col-4
    min-height: calc(100vh - (var(--sameContextGap) * 2))
</style>