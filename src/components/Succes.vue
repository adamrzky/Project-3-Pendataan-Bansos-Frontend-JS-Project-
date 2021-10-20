<template>
    <v-dialog
        v-model="dialog"
        persistent
        max-width="400"
        content-class=".rounded-t-xl text-center"
    >
        <v-card>

            <v-card-title class="d-block text-h4 text-center error--text">
                 Tersimpan
            </v-card-title>

            <div class="px-5 mb-2">
                <v-divider></v-divider>
            </div>

            <v-card-text> Tersimpan</v-card-text>
            
            <div class="px-5">
                <v-btn
                    color="error rounded-pill py-6"
                    block
                    @click="dialog = false"
                >
                    OK
                </v-btn>
            </div>
        </v-card>
    </v-dialog>
</template>

<script>
    import { mapGetters, mapActions } from "vuex";

    export default {
        name: "Dialog",
        computed:{
            ...mapGetters({
                "DialogSucces" : "dialog/succes"
            }),
            dialog: {
                get() {
                    return this.DialogSucces;
                },
                set(value) {
                    this.setDialogSucces(value);
                },
            },
        },
        methods:{
            ...mapActions({
                "setDialogSucces" : "dialog/setSucces"
            })
        }
    }
</script>