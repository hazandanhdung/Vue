<template>
    <v-container>
        <v-layout
                text-xs-center
                wrap
        >
            <v-flex xs12>
                <v-img
                        :src="require('../assets/logo.svg')"
                        class="my-3"
                        contain
                        height="200"
                ></v-img>
            </v-flex>

            <v-flex xs12>
               <!--<div class="text-sm-center">-->
                   <!--<v-bottom-sheet v-model="sheet">-->
                       <!--<template v-slot:activator>-->

                           <!--<v-btn color="purple" dark>Click Me</v-btn>-->
                       <!--</template>-->
                       <!--<v-lits>-->
                           <!--<v-subheader>Open in</v-subheader>-->
                           <!--<v-list-tile  v-for="tile in tiles"-->
                                         <!--:key="tile.title"-->
                                         <!--@click="sheet = false" >-->
                               <!--<v-list-tile-avatar>-->
                                   <!--<v-avatar size="32px" tile>-->
                                       <!--<img-->
                                               <!--:src="`https://cdn.vuetifyjs.com/images/bottom-sheets/${tile.img}`"-->
                                               <!--:alt="tile.title"-->
                                       <!--&gt;-->
                                   <!--</v-avatar>-->
                               <!--</v-list-tile-avatar>-->
                            <!--<v-list-tile-title>{{tile.title}}</v-list-tile-title>-->
                           <!--</v-list-tile>-->
                       <!--</v-lits>-->
                   <!--</v-bottom-sheet>-->

               <!--</div>-->
                <div class="text-xs-center">
                    <v-bottom-sheet v-model="sheet">
                        <template v-slot:activator>
                            <v-btn
                                    color="purple"
                                    dark
                            >
                                Click me
                            </v-btn>
                        </template>
                        <v-list>
                            <v-subheader>Open in</v-subheader>
                            <v-list-tile
                                    v-for="tile in tiles"
                                    :key="tile.title"
                                    @click="sheet = false"
                            >
                                <v-list-tile-avatar>
                                    <v-avatar size="32px" tile>
                                        <img
                                                :src="`https://cdn.vuetifyjs.com/images/bottom-sheets/${tile.img}`"
                                                :alt="tile.title"
                                        >
                                    </v-avatar>
                                </v-list-tile-avatar>
                                <v-list-tile-title>{{ tile.title }}</v-list-tile-title>
                            </v-list-tile>
                        </v-list>
                    </v-bottom-sheet>
                </div>
                <div class="text-md-center">
                    <div>
                        <v-tabs
                                v-model="active"
                                color="cyan"
                                dark
                                slider-color="yellow"
                        >
                            <v-tab
                                    v-for="n in 3"
                                    :key="n"
                                    ripple
                            >
                                Item {{ n }}

                            </v-tab>
                            <v-tab-item
                                    v-for="n in 3"
                                    :key="n"
                            >
                                <v-card flat>
                                    <v-card-text>{{ text }}</v-card-text>
                                </v-card>
                            </v-tab-item>
                        </v-tabs>

                        <div class="text-xs-center mt-3">
                            <v-btn @click="next">next tab</v-btn>
                        </div>
                    </div>
                    <!--<v-checkbox-->
                            <!--v-model="checkbox"-->
                            <!--:label="`: ${checkbox.toString()}`"-->
                    <!--&gt;</v-checkbox>-->
                    <!--<v-radio-group v-model="radioGroup">-->
                        <!--<v-radio-->
                                <!--v-for="n in 3"-->
                                <!--:key="n"-->
                                <!--:label="`Radio ${n}`"-->
                                <!--:value="n"-->
                        <!--&gt;</v-radio>-->
                    <!--</v-radio-group>-->
                    <!--<v-switch-->
                            <!--v-model="switch1"-->
                            <!--:label="` ${switch1.toString()}`"-->
                    <!--&gt;</v-switch>-->
                </div>
                <v-container fluid class="text-xs-center">
                    <v-layout
                            justify-space-between
                            row
                            wrap
                    >
                        <v-flex xs12>
                            <v-btn
                                    color="indigo"
                                    class="white--text"
                                    @click="show = !show"
                            >
                                Toggle
                            </v-btn>
                        </v-flex>

                        <v-flex xs12 class="mt-5">
                            <v-badge
                                    v-model="show"
                                    color="cyan"
                                    left
                            >
                                <template v-slot:badge>
                                    <span>6</span>
                                </template>
                                <v-icon
                                        large
                                        color="grey lighten-1"
                                >shopping_cart</v-icon>
                            </v-badge>

                            <v-badge
                                    v-model="show"
                                    color="purple"
                            >
                                <template v-slot:badge>
                                    <span>6</span>
                                </template>
                                <v-icon large color="grey">mail</v-icon>
                            </v-badge>
                        </v-flex>
                    </v-layout>
                </v-container>


            </v-flex>

        </v-layout>
    </v-container>
</template>

<script>
    export default {
        data: () => ({
            active: null,
            text : 'the resulting language is more simple and regular tha ' +
                'The new common language will be more simple and regular than th ' +
                'It will be as simple as Occide ',
            method : {
                next(){
                    const  active = parent(this.active)
                    this.active = (active < 2 ? active + 1 : 0)
                }
            },
            checkbox : true,

            radioGroup: 1,
            switch1: true,
            sheet : false,
            show: true,
            tiles : [
                {img : 'keep.png', title: 'Keep'},
                {img : 'inbox.png', title: 'Inbox'},
                {img : 'hangouts.png', title: 'Hangouts'},
                {img : 'messenger.png', title: 'Messenger'},
                {img : 'google.png', title: 'Google+'},
            ],

            // ecosystem: [
            //     {
            //         text: 'vuetify-loader',
            //         href: 'https://github.com/vuetifyjs/vuetify-loader'
            //     },
            //     {
            //         text: 'github',
            //         href: 'https://github.com/vuetifyjs/vuetify'
            //     },
            //     {
            //         text: 'awesome-vuetify',
            //         href: 'https://github.com/vuetifyjs/awesome-vuetify'
            //     }
            // ],
            // importantLinks: [
            //     {
            //         text: 'Documentation',
            //         href: 'https://vuetifyjs.com'
            //     },
            //     {
            //         text: 'Chat',
            //         href: 'https://community.vuetifyjs.com'
            //     },
            //     {
            //         text: 'Made with Vuetify',
            //         href: 'https://madewithvuetifyjs.com'
            //     },
            //     {
            //         text: 'Twitter',
            //         href: 'https://twitter.com/vuetifyjs'
            //     },
            //     {
            //         text: 'Articles',
            //         href: 'https://medium.com/vuetify'
            //     }
            // ],
            // whatsNext: [
            //     {
            //         text: 'Explore components',
            //         href: 'https://vuetifyjs.com/components/api-explorer'
            //     },
            //     {
            //         text: 'Select a layout',
            //         href: 'https://vuetifyjs.com/layout/pre-defined'
            //     },
            //     {
            //         text: 'Frequently Asked Questions',
            //         href: 'https://vuetifyjs.com/getting-started/frequently-asked-questions'
            //     }
            //
            // ]
        })
    }
</script>

<style>

</style>
