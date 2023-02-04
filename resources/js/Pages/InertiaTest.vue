<script setup>
import { Link } from '@inertiajs/vue3';
import { ref } from 'vue'

const newTitle = ref('');
const newContent = ref('');

</script>

<template>
    <p>InertiaTestです. </p> <br>
    <a href="/">aタグ経由</a> <br>
    <Link href="/">Link経由</Link> <br>
    <Link :href="route('inertia.index')">名前つきrouteの確認</Link> <br>
    <Link :href="route('inertia.show', {id : 1} )">ルートパラメーターの確認</Link>

    <div class="mb-8">
        <input type="text" name="newTitle" v-model="newTitle"> <br>
        <input type="text" name="newContent" v-model="newContent"> <br>
        <Link as="button" method="post" :href="route('inertia.store')" 
        :data="{ 
            title : newTitle,
            content : newContent
         }">DB保存</Link>
    </div>

    


</template>