<template>
  <Layout>
    <h2>Latest blog posts</h2>
    <ul>
      <li v-for="edge in $page.allPost.edges" :key="edge.node.id">
        {{ edge.node.title }}
      </li>
    </ul>
  </Layout>
</template>

<page-query>
query Post {
  allPost (limit: 5) {
    edges {
      node {
        title
        excerpt
      }
    }
  }
}
</page-query>