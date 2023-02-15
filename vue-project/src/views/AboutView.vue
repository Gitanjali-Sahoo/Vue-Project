<script setup>
    import Form from '../components/Form.vue'
    import Footer from '../components/Footer.vue'
</script>

<template>
    <Form />
    <div id="footer">
        <Footer />
    </div>
</template>

<style scoped>
    #footer {
        background-color: rgb(225, 220, 197);
        padding: 20px;
        position: sticky;
    }
</style>
