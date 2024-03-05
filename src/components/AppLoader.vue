<script>
export default {
    name: 'AppLoader',
}
</script>

<template>
    <div id="loader-wrapper">
        <div class="loader"></div>
    </div>
</template>

<style lang="scss">

#loader-wrapper {

    position: absolute;
    left: 0;
    top: 0;

    width: 100%;
    height: 100%;

    background-color: black;

    .loader {
    position: absolute;
    top: 10%;
    left: 40%;
    width: 200px;
    padding: 28px;
    aspect-ratio: 1;
    border-radius: 50%;
    background: #FFFFFF;
    --_m: 
        conic-gradient(#0000 10%,#000),
        linear-gradient(#000 0 0) content-box;
    -webkit-mask: var(--_m);
            mask: var(--_m);
    -webkit-mask-composite: source-out;
            mask-composite: subtract;

    animation: l3 1s infinite linear;
}

@keyframes l3 {to{transform: rotate(1turn)}}
}
    
</style>