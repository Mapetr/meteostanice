<template>
    <div>
        <br>
        <div class='line'>
        <h2 class='left'>{{leftName}}</h2>
        <h2 class='right'>{{rightName}}</h2>
        </div>
        <br>
        <div class='line'>
        <h3 class='left'>{{left}}</h3>
        <h3 class='right'>{{right}}</h3>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'HomeLine',
        props: {
            leftName: String,
            left: String,
            rightName: String,
            right: String,
        },
    }
</script>

<style scoped>
.line {
    width: 100%;

    display: flex;
    align-items: center;
}

.left {
    width: 100%;
    margin: 0 0 0 12%;
}

.right {
    width: 100%;
    text-align: right;
    margin: 0 12% 0 0;
}
</style>