<template>
  <main class="main">
  <div class="top-green-line"></div>
    <hero class="hero-intro is-primary" containerClass="container-thin" withEntry title="Blog">
      <template slot="entry">
        <p>Airship news, announcements, best practices, use cases and more.</p>
      </template>
    </hero>

    <div class="main-inner">
      <div class="container container-thin">
        <h4 class="main-title" style="display: none">All Posts</h4>
        <!-- /.main-title -->
        <br>
        <div class="main-container">
          <div class="content">
            <PostList :author="author" :category="category"/>
          </div>
          <!-- /.content -->
          <aside class="sidebar">
            <ul class="widgets">
              <li class="widget">
                <div class="widget-head">
                  <h6 class="widget-title">Categories</h6>
                  <!-- /.widget-title -->
                </div>
                <!-- /.widget-head -->
                <div class="widget-body">
                  <ul class="widget-list">
                    <li>
                      <router-link to="/blog/?category=news">News &amp; Announcements</router-link>
                    </li>

                    <li>
                      <router-link to="/blog/?category=software">Software</router-link>
                    </li>

                    <li>
                      <router-link to="/blog/?category=use-cases">Use Cases</router-link>
                    </li>

                    <li>
                      <router-link to="/blog/?category=features-and-updates">Features & Updates</router-link>
                    </li>
                  </ul>
                  <!-- /.widget-list -->
                </div>
                <!-- /.widget-body -->
              </li>
              <!-- /.widget -->
              <li class="widget">
                <div class="widget-head">
                  <h6 class="widget-title">Connect</h6>
                  <!-- /.widget-title -->
                </div>
                <!-- /.widget-head -->
                <div class="widget-body">
                  <ul class="widget-list">
                    <li>
                      <a href="http://lists.katacontainers.io/cgi-bin/mailman/listinfo">Mailing Lists</a>
                    </li>

                    <li>
                      <a href="https://wiki.openstack.org/wiki/Airship#Get_in_Touch">Weekly Calls</a>
                    </li>

                    <li>
                      <a href="https://wiki.openstack.org/wiki/Airship#Get_in_Touch ">Freenode IRC: #airshipit</a>
                    </li>

                    <li>
                      <a href="https://twitter.com/airshipproject">Twitter</a>
                    </li>
                  </ul>
                  <!-- /.widget-list -->
                </div>
                <!-- /.widget-body -->
              </li>
              <!-- /.widget -->
            </ul>
            <!-- /.widgets -->
          </aside>
          <!-- /.sidebar -->
        </div>
        <!-- /.main-container -->
      </div>
      <!-- /.container -->
    </div>
    <!-- /.main-inner -->
  </main>
  <!-- /.main -->
</template>

<script>
import PostList from "./PostList.vue";

export default {
  /**
   * The name of the component.
   *
   * @type {Strng}
   */
  name: "Blog",

  components: { PostList },

  /**
   * Internal state of the component.
   *
   * @return {Object}
   */
  data: () => ({
    total: 200,
    current: 2,
    perPage: 20
  }),
  computed: {
    category() {
      return this.$route.query.category || "all";
    },
    author() {
      return this.$route.query.author || "any";
    }
  }
};
</script>
