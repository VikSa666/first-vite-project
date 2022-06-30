<template>
    <div>
        <p>{{ name }}</p>
        <input ref="el" type="text" placeholder="Name" v-model="name"/>
        <div>
            <button 
            :disabled="name.length == 0" 
            @click="submitForm"
            >
            Submit
            </button>
        </div>
    </div>
</template>

<script>
import { ref, onMounted } from 'vue'

export default {
    setup() {
        const name = ref('')
        const el = ref()
        const submitForm = () => {
            console.log(`Form submitted! Name = ${name.value}`)
        }

        onMounted(() => {
            el.value.focus()
        })
        return {
            name,
            el,
            submitForm,
        }
    }
}
</script>

<style>
    input[type='text'] {
        padding: 5px
    }

    button {
        margin-top: 20px;
    }
</style>