<template>
  <Layout>
    <section class="hero is-warning is-bold">
      <div class="hero-body">
        <div class="container has-text-centered">
          <h1 class="title is-1">
            {{ $page.metadata.siteDescription }}
          </h1>
        </div>
      </div>
    </section>

    <div
      v-for="project in $page.projects.edges"
      :key="project.node.id"
      class="container bg-blue-400 min-w-full h-64"
    >
      {{ project.node.title }}
    </div>
  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: 'Мой персональный сайт',
  }
}
</script>

<page-query>
query {
  projects: allProject {
    edges {
      node {
        id
        path
        title
        url
        content
      }
    }
  }
  metadata {
    siteDescription
  }
}
</page-query>
