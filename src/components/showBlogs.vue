<template>
    <div id="show-blogs">
        <h2>All Post Blogs</h2>
        <input type="text" v-model="search" placeholder="search blogs" />
        <div v-for="blog in filteredBlogs" class="single-blog">
            <h2 v-rainbow>{{ blog.title | toUppercase }}</h2>
            <article>{{ blog.body | snippet}}</article>
        </div>
    </div>
</template>

<script>
// Imports

export default {
    data () {
        return {
           blogs:[],
           search:''
        }
    },
    methods: {
      
    },
    computed: {
         filteredBlogs: function() {
            return this.blogs.filter((blog) => {
                return blog.title.match(this.search);
            })
        }
    },
    created() {
        this.$http.get('http://jsonplaceholder.typicode.com/posts').then(function(data){
            this.blogs = data.body.slice(0,10);
        })
    },
    filters: {
        toUppercase (value) {
            return value.toUpperCase();
        }
    },
    directives: {
        'rainbow': {
            bind(el, binding, vnode) {
                el.style.color = '#' + Math.random().toString(16).slice(2,8);
            }
        }
    }
}
</script>

<style>
#show-blogs {
    max-width: 800px;
    margin: 0 auto;
}
.single-blog {
    padding: 20px;
    margin: 20px 0;
    box-sizing: border-box;
    background: #eee;
}
</style>