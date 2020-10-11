<template>
  <Layout>
    <h1>{{ $page.project.title }}</h1>
    <div>{{ $page.project.content }}</div>
  </Layout>
</template>

<page-query>
query Project($path: String) {
  project: project(path: $path) {
    title
    content
  }
}
</page-query>
