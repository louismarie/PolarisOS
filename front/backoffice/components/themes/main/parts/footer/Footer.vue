<template>
<footer class="section">
    <div class="footer-container container is-fluid is-marginless">
        <div class="columns footer-disclaimer">
            <p class="column" v-html="lang('l_footer_disclaimer')"></p>
        </div>
    </div>
</footer>
</template>

<script>
    module.exports = require('./Footer');
</script>
