<template lang="html">
<div class="row">
    <div class="col-12" v-if="!$nuxt.$route.params.id">
        <h1>エラーが発生しました</h1>
        <h2>再度ログインをお願いします</h2>
        <button class="btn btn-large btn-danger" @click="$router.push('/login')">ログイン</button>
    </div>
    
    <div class="col-12" v-else>
        <h1>エラーが発生しました</h1>
        <button class="btn btn-info" @click="reloadPage()">再読み込み</button>
    </div>
</div>
</template>

<script>
export default {
    props: ['error'],
    methods: {
        reloadPage:function(){
            this.$router.go({path: this.$router.currentRoute.path, force: true})
        }
    }
}
</script>