<template>
    <header>
        <a class="nav-item nav-link" href="http://localhost:5173/">
            <div class="blog_icon">
                <div>
                    <img src="/header_icon.svg" width="50" height="50" class="d-inline-block align-top" alt="">
                </div>

                <div class="blog_title">
                    <h1>Il Blog che ti fa volare...</h1>
                </div>
            </div>
        </a>
    </header>
</template>
  
<script>
export default {
    // I tuoi metodi o dati se necessario
};
</script>
  
<style lang="scss">
@import '../styles/partials/mixins';
@import '../styles/partials/variables';

header {
    position: fixed;
    width: 100%;
    z-index: 1000;
    background-color: $header-bg-color;
    height: 80px;
    top: 0;
    @include flex-start-center;

    a {
        .blog_icon {
            display: flex;
            color: rgb(255, 255, 255);

            .blog_title {
                h1:hover {
                    color: rgb(145, 255, 0);
                    text-shadow: 3px 3px 2px black;
                }
            }
        }
    }

}
</style>