<template>
    <v-dialog
        v-model="dialog"
        persistent
        max-width="400"
        content-class=".rounded-t-xl text-center"
    >
        <v-card>

            <v-card-title class="d-block text-h4 text-center error--text">
                Gagal Tersimpan
            </v-card-title>

            <div class="px-5 mb-2">
                <v-divider></v-divider>
            </div>

            <v-card-text>Gagal Tersimpan, Coba Lagi</v-card-text>
            
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
                "dialogStatus" : "dialog/status"
            }),
            dialog: {
                get() {
                    return this.dialogStatus;
                },
                set(value) {
                    this.setDialogStatus(value);
                },
            },
        },
        methods:{
            ...mapActions({
                "setDialogStatus" : "dialog/setStatus"
            })
        }
    }
</script>