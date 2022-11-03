<template>
    <div style="padding:30px;">
      <el-alert :closable="false" title="文档" />
          <div id="content" v-html="compiledMarkdown"></div>
    </div>
    <!-- <div id="content">
    </div> -->

  </template>

    <script>
    import { marked } from 'marked'
    import { mapGetters } from 'vuex'
    // var content='m';
    // content=marked.parse('# Marked in browser\n\nRendered by **marked**.')
    // console.log(content)
    // document.getElementById('content').innerHTML =content
      
   
export default {
  name: 'Dashboard',
  data () {
    var content=marked.parse('# Marked in browser\n\nRendered by **marked**.');
    return {
      articleDetail: {
        context:
          "# Marked in browser\n\nRendered by **marked**.",
          //读取数据库中的markdown文件。。。
          
      }

    }
  },
  computed: {
    ...mapGetters(['name']),
    compiledMarkdown() {
      return marked.parse(this.articleDetail.context);
    },
  }
}
    
  </script>
  