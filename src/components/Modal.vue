<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal">
            <slot></slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props:["header","footer"],
    methods:{
        closeModal(){
            this.$emit("closeModal")
        }
    }
}
</script>

<style scoped>
    body{
        margin: 0;
        padding: 0;
    }
    .backdrop{
        position: fixed;
        top: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.5);
    }
    .modal{
        background:#fff;
        width: 400px;
        margin: 100px auto;
        padding: 10px;
        border-radius: 10px;
    }
</style>