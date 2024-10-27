<template>
      <form @submit.prevent="submitForm">
        <input type="text" v-model="city" placeholder="都市名を英語で入力">
        <button type="submit">Get Weather</button>
    </form>
</template>

<script setup>
    import { ref } from "vue"

    const city = ref("")

    //上位コンポーネントに対して放出する仕組み
    const submitForm = () => {
        emits("submit-form", city.value)
        city.value = ""
    }

    //放出する仕組みの定義
    const emits = defineEmits([
        "submit-form"
    ])
</script>
