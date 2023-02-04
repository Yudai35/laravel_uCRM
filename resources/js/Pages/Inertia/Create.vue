<script setup>
import { reactive } from 'vue'
import { Inertia } from '@inertiajs/inertia'

const form = reactive({
    title: null,
    content: null
})

const submitFunction = () => {
    Inertia.post('/inertia', form)
}


</script>


<template>
    <p>クリエイト</p>
    <form @submit.prevent="submitFunction">
        <input name="title" type="text" v-model="form.title"> <br>
        <input name="content" type="text" v-model="form.content">
        <button>送信</button>
    </form>
</template>