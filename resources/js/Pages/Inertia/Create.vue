<script setup>
import { reactive } from 'vue'
import { Inertia } from '@inertiajs/inertia'

defineProps({
    errors: Object
})

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
        <div class="text-red-600" v-if="errors.title">{{ errors.title }}</div>
        <input name="content" type="text" v-model="form.content"> <br>
        <div class="text-red-600" v-if="errors.content">{{ errors.content }}</div>
        <button>送信</button>
    </form>
</template>