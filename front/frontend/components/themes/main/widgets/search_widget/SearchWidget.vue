<template>
<div v-if="mode === 'all' || mode === 'small'">
    <div class="columns is-centered" v-if="mode !== 'small'">
        <div class="column has-text-centered is-8">
            <h4 class="title is-4">{{lang('f_search_info')}}</h4>
            <p v-html="lang('f_search_help')"></p>
        </div>
    </div>
    <div class="columns is-centered">
        <div class="column">
            <form @submit.prevent="trigger_click">
                <div class="field has-addons">
                    <p class="control has-icons-left is-expanded">
                        <finput type="text" :placeholder="lang('f_search_in_archive')" name="search" :form="state.forms.ssink" label="" />
                        <span class="icon is-left">
                            <i class="fa fa-search"></i>
                        </span>
                        </p>
                    <p class="control">
                        <a class="icon has-text-info is-large" :alt="lang('f_search')" :title="lang('f_search')" @click="trigger_click">
                            <i class="fa fa-search fa-2x"></i>
                        </a>
                    </p>
                    <p class="control">
                        <a class="icon has-text-warning is-large" :alt="lang('f_save_search')" :title="lang('f_save_search')">
                            <i class="fa fa-star-o fa-2x"></i>
                        </a>
                    </p>
                </div>
                <div class="field">
                    <div class="control">
                        <a @click="state.more_options = !state.more_options" class="swap">{{lang('f_advanced_search')}}</a>
                    </div>
                </div>
                <div v-if="state.more_options">
                    <div :class="['card', 'info-card']">
                        <div class="card-content">
                            <fselect cform="test_form" label="Filtrer par auteur" :options="[{label: 'Corentin Ribeyre', value: 'cribeyre'}, {label: 'Yann Mahé', value: 'ymahe'}, {label: 'Marie Candito', value: 'mcandito'}, {label: 'Karin Sohler', value:'ksohler'}]" :multi="true" />
                            <fselect cform="test_form" label="Filtrer par année" :options="[{label: '2017', value: 2017}, {label: '2016', value: 2016}, {label: '2015', value: 2015}]" :multi="true" />
                            <fselect cform="test_form" label="Filtrer par domaine" :options="[]" :multi="true" />
                            <fselect cform="test_form" label="Filtrer par type de publication" :options="[]" :multi="true" />
                            <fselect cform="test_form" label="Filtrer par journal / conférence" :options="[]" :multi="true" />
                            <div class="control">
                                <button class="button">Valider</button>
                            </div>
                        </div>
                    </div>
                </div>
            </form>
        </div>
    </div>
</div>
<div v-else-if="mode === 'on-side'">
    <form @submit.prevent="trigger_click">
        <div class="field has-addons">
            <p class="control has-icons-left is-expanded">
                <finput type="text" :placeholder="lang('f_search_in_archive')" name="search" :form="state.forms.ssink" label="" />
                <span class="icon is-left">
                    <i class="fa fa-search"></i>
                </span>
                </p>
                <p class="control">
                    <a class="icon has-text-info is-large" :alt="lang('f_search')" :title="lang('f_search')" @click="trigger_click">
                        <i class="fa fa-search fa-2x"></i>
                    </a>
            </p>
        </div>
    </form>
</div>
</template>

<script>
    module.exports = require('./SearchWidget');
</script>
