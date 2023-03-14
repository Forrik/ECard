<template>
    <button class="btn">
        <slot></slot>
    </button>
</template>

<script>
    export default {
        name: 'my-button'
    }
</script>

<style scoped>

.btn {
    padding: 5px 20px;
    font-weight: 600;
    background-color: #c31010;
    border-color: #a80a0a;
    box-shadow: 0 5px 10px -5px #c31010;
    color: white;
    border-radius: 20px;
    cursor: pointer;
 
}

.btn:hover {
    background-color: #1060bc;
    box-shadow:  0 5px 10px -5px #1060bc;
    transition:all .4s ease-in;
    border-color: #07257e;
}

</style>