<template>
  <div class="container-fluid text-white mt-5">
    <div class="row text-center">
      <h4 class="fst-italic mb-3">Backend Projects</h4>
      <hr class="border border-1" />
    </div>
    <Projects :projects="projects" />
  </div>
</template>

<script>
import Project from '@/api/portfolio/Projects';
import Projects from '@/components/projects/Projects.vue';

export default {
  name: 'Backend-V',
  components: {
    Projects,
  },
  data() {
    return {
      projects: [],
    };
  },
  async mounted() {
    this.projects = await Project.GetByCategory('backend');
  },
};
</script>
