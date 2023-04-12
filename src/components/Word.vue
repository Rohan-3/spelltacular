<template>
    <v-card outlined>
        <v-container>
            <v-row dense align="center" justify="center">
                <div class="display-6" v-if="!spelling.length">Spell the Word by clicking below elements</div>
                <v-col
                    v-for="(e,i) in spelling"
                    :key="i"
                    class="d-flex child-flex"
                    style="padding: 5px"
                    :cols="
                        $vuetify.breakpoint.xsOnly
                        ? 3
                        : $vuetify.breakpoint.smAndDown
                            ? 2
                            : 1
                    "
                    @click="$emit('remove', i);"
                >
                    <tile
                        :letter="e.letter"
                        :vowel="e.vowel"
                        :image="e.image"
                        :alt="e.alt"
                    />
                </v-col>
                <v-btn text icon x-large v-if="spelling.length" @click="$emit('clear')">
                    <v-icon x-large color="red">mdi-close</v-icon>
                </v-btn>
            </v-row>
        </v-container>
    </v-card>
</template>

<script lang="js">
import Tile from "@/components/Tile.vue";

export default {
  name: "Word",
  components: {
    Tile
  },
  props: {
    spelling: { type: Array, required: true }
  },
  methods: {
      //
  },
  data: () => ({
  })
};
</script>

<style lang="js">

</style>