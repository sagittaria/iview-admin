<template>
<div>
    <Row :gutter="16">
        <Col span="12">
            <Card>
                <p slot="title">新增用户</p>
                <user-create></user-create>
            </Card>
        </Col>
        <Col span="12">
            <Card>
                <user-retrieve></user-retrieve>
            </Card>
        </Col>
    </Row>
    <Row>
        <Col span="12">
            <Card>
                <user-update></user-update>
            </Card>
        </Col>
        <Col span="12">
            <Card>
                <user-delete></user-delete>
            </Card>
        </Col>
    </Row>
</div>
</template>

<script>
    import userCreate from './components/user-create.vue';
    import userRetrieve from './components/user-retrieve.vue';
    import userUpdate from './components/user-update.vue';
    import userDelete from './components/user-delete.vue';
    import Row from 'iview/src/components/grid/row';
    export default {
        name: 'user',
        components: {
            Row,
            userCreate,
            userRetrieve,
            userUpdate,
            userDelete
        }
    };
</script>

<style scoped>

</style>
