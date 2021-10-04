<template>
    <div class="form-group">
        <input type="text" class="form-control" placeholder="いま何してる？">
        <button type="submit" class="btn btn-primary">ツイート</button>
        <p>{{msg}}</p>
    </div>
</template>

<script>
export default {
    name: 'Form',
    props: {
        msg: String,
    },
    data() {
        return {
            
        }
    }
}
</script>