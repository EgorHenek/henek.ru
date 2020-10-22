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

    <div class="section">
      <div class="container">
        <h3 class="title is-3">
          Мои проекты
        </h3>
        <div class="columns">
          <div
              v-for="project in $page.projects.edges"
              :key="project.node.id"
              class="column is-one-third-desktop is-full-mobile is-half-tablet"
          >
            <div class="card">
              <div class="card-image">
                <figure class="image is-4by3">
                  <g-image :src="project.node.image" />
                </figure>
              </div>
              <div class="card-content">
                <div class="media">
                  <div class="media-left">
                    <figure class="image is-48x48">
                      <g-image :src="project.node.logo" />
                    </figure>
                  </div>
                  <div class="media-content">
                    <p class="title is-4">
                      <a
                          :href="project.node.url"
                          target="_blank"
                      >{{ project.node.title }}</a>
                    </p>
                    <p class="subtitle is-6">{{ project.node.subtitle}}</p>
                  </div>
                </div>

                <div
                    class="content"
                    v-html="project.node.content"
                />
              </div>
            </div>
        </div>
        </div>
      </div>
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
  projects: allProject(sortBy: "id") {
    edges {
      node {
        id
        path
        title
        url
        content
        logo
        image
        subtitle
      }
    }
  }
  metadata {
    siteDescription
  }
}
</page-query>
