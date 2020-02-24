<template>
    <div class="col-sm-6 col-md-4 col-lg-3">
        <div class="panel panel-default">
            <div class="panel-body quote">
                <slot></slot>
            </div>      
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
    .panel-body{
        font-family: 'Trade Winds', ;
        font-size: 24px;
        color: rgb(31, 141, 214);
        text-align: center;
    }

    .quote {
        cursor: pointer;
    }

    .quote:hover {
        background-color: rgba(216, 126, 126, 0.795);
    }

</style>