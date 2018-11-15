<template>
    <div class="col">
        <div class="col-sm-12">
            <h3>Quotes Added</h3>
            <div class="progress">
                <div class="progress">
                    <div class="progress-bar" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100"
                    :style="{width: (quote_count/ max_quotes) * 100 + '%'}">
                        {{ quote_count }} / {{ max_quotes }}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['quote_count', 'max_quotes']
    }
</script>