<template>
  <Layout>
    <h2>Latest blog posts</h2>
    <ul>
      <li v-for="edge in $page.allWordPressPost.edges" :key="edge.node.id">
        {{ edge.node.title }}
      </li>
    </ul>
  </Layout>
</template>

<page-query>
query Post {
  Post (limit: 5) {
    edges {
      node {
        _id
        title
      }
    }
  }
}
</page-query>