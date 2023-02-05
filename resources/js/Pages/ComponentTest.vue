<script setup>
import GuestLayout from '@/Layouts/GuestLayout.vue'
import InputLabel from '@/Components/InputLabel.vue'
import Input from '@/Components/Input.vue'

const emitTest = e => console.log(e)

</script>

<template>
    <GuestLayout>
    <InputLabel value="件名">タイトル</InputLabel>
    <Input 
        modelValue="初期値が入ります"
        @update:modelValue="emitTest"    
    ></Input>
</GuestLayout>

</template>