<template>
    <Row>
        <Col span="14">
            <Form :model="newUser" label-position="right" :label-width="80">
                <Form-item label="name">
                    <Input v-model="newUser.name" placeholder="username" style="width: 215px;"></Input>
                </Form-item>
                <Form-item label="gender">
                    <RadioGroup v-model="newUser.gender">
                        <Radio label="male"></Radio>
                        <Radio label="female"></Radio>
                    </RadioGroup>
                </Form-item>
                <Form-item label="birthday">
                    <DatePicker type="date" @on-change="setBirthday"
                                placeholder="Select birthday" style="width: 215px;"></DatePicker>
                </Form-item>
                <Form-item label="hobby">
                    <CheckboxGroup v-model="newUser.hobby">
                        <Checkbox label="jogging"></Checkbox>
                        <Checkbox label="swimming"></Checkbox>
                        <Checkbox label="boxing"></Checkbox>
                    </CheckboxGroup>
                </Form-item>
                <Form-item label="major">
                    <Select v-model="newUser.major" style="width: 215px;">
                        <Option v-for="item in majorList" :value="item.value" :key="item.value">{{ item.label }}</Option>
                    </Select>
                </Form-item>
                <FormItem>
                    <Button type="primary">Submit</Button>
                    <Button style="margin-left: 8px">Reset</Button>
                </FormItem>
            </Form>
        </Col>
        <Col span="10">
            <ul style="border: 1px solid darkgray">
                <li v-for="(value, key) in newUser">
                    {{ key }}: {{ value }}
                </li>
            </ul>
        </Col>
    </Row>
</template>

<script>
    import FormItem from 'iview/src/components/form/form-item';

    export default {
        components: {FormItem},
        name: 'create',
        data () {
            return {
                newUser: {
                    name: '',
                    gender: '',
                    birthday: '',
                    hobby: [],
                    major: ''
                },
                majorList: [
                    {
                        value: 'math',
                        label: 'math'
                    },
                    {
                        value: 'physics',
                        label: 'physics'
                    },
                    {
                        value: 'philosophy',
                        label: 'philosophy'
                    }
                ]
            };
        },
        methods: {
            setBirthday: function (value) {
                this.newUser.birthday = value;
                // 用箭头函数里this指向的不是vue实例
                // 所以methods里不要用箭头函数
            }
        }
    };
</script>

<style scoped>

</style>
