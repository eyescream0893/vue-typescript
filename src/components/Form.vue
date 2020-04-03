<template>
    <div>
    </div>
</template>

<script lang="ts">
import Vue from "vue"
export default {
    data: () => ({
        defaultDateLabel: "1980-01-01",
        dateLabel: null as string | null
    }),
    computed: {
        dateFormDateLabel(): Date {
            let label = this.defaultDateLabel
            if (this.dateLabel !== null) {
                label = this.dateLabel
            }
            return new Date(label)
        }
    }
}
</script>