<template>
  <div class="container-fluid text-white mt-5">
    <div class="row text-center">
      <h4 class="fst-italic mb-3">Web Projects</h4>
      <hr class="border border-1" />
    </div>
    <Projects :projects="projects" />
  </div>
</template>

<script>
import Projects from '@/components/projects/Projects';
import Project from '@/api/portfolio/Projects';

export default {
  name: 'Web-V',
  data() {
    return {
      projects: [],
    };
  },
  components: {
    Projects,
  },
  async mounted() {
    this.projects = await Project.GetByCategory('web');
  },
};
</script>
