<template>
  <v-container fluid class="pb-10">
    <h1 class="text-center py-5">Portfolio</h1>
    <v-col cols="12" md="11" xl="10" class="mx-auto">
      <card-list-transition class="row">
        <v-col
          cols="12"
          sm="6"
          md="4"
          v-for="project in projects"
          :key="project.name"
        >
          <project-detail v-bind="project" />
        </v-col>
      </card-list-transition>
    </v-col>
  </v-container>
</template>
<script lang="ts">
import { defineComponent } from "@vue/composition-api";
import ExpandableCard from "@/components/core/ExpandableCard.vue";
import ProjectDetail from "@/components/portfolio/ProjectDetail.vue";
import CardListTransition from "@/components/transitions/CardListTrasition.vue";
import { projects } from "@/data/portfolio";

export default defineComponent({
  name: "Portfolio",
  components: {
    CardListTransition,
    ProjectDetail,
    ExpandableCard,
  },
  data() {
    return {
      projects,
    };
  },
});
</script>
