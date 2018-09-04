<template>
    <div class="row">
        <div class="col-sm-12">
            <div class="progress">
                <div class="progress-bar" aria-valuenow="70" aria-valuemin="0" aria-valuemax="100"  role="progressbar" v-bind:style="{width: (quoteCount/maxQuote) * 100 + '%'}">
                    {{ quoteCount / maxQuote * 100}} %
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default{
    props:['quoteCount','maxQuote']
}
</script>
