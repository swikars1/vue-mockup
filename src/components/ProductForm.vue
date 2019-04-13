<template>
    <Form ref="formValidate" :model="formValidate" :rules="ruleValidate" label-position="top" style="margin-left: 8px">
        <FormItem label="Title" prop="name">
            <Input v-model="formValidate.name" placeholder="Enter the title"></Input>
        </FormItem>
        <FormItem label="Desc" prop="desc">
            <Input v-model="formValidate.desc" type="textarea" :autosize="{minRows: 2,maxRows: 5}" placeholder="Enter something..."></Input>
        </FormItem>
        <FormItem label="Status" prop="status">
            <Select v-model="formValidate.status" placeholder="Select the status">
                <Option value="New">New</Option>
                <Option value="Completed">Completed</Option>
                <Option value="In_Progress">In_Progress</Option>
            </Select>
        </FormItem>
        <FormItem label="Start-Date">
            <Row>
                <Col span="11">
                    <FormItem prop="sdate">
                        <DatePicker type="date" placeholder="Select Start-Date" v-model="formValidate.sdate"></DatePicker>
                    </FormItem>
                </Col>
            </Row>
        </FormItem>
        <FormItem label="End-Date">
            <Row>
                <Col span="11">
                    <FormItem prop="edate">
                        <DatePicker type="date" placeholder="Select End-Date" v-model="formValidate.edate"></DatePicker>
                    </FormItem>
                </Col>  
            </Row>
        </FormItem>

        <FormItem>
            <Button type="primary" @click="handleSubmit('formValidate')">Create</Button>
            <Button @click="handleReset('formValidate')" style="margin-left: 8px">Reset</Button>
        </FormItem>
    </Form>
</template>

<script>
    export default {
        data () {
            return {
                formValidate: {
                    name: '',
                    desc: '',
                    status: '',
                    sdate: '',
                    edate: ''
                },
                ruleValidate: {
                    name: [
                        { required: true, message: 'The name cannot be empty', trigger: 'blur' }
                    ],
                    desc: [
                        { required: false }
                    ],
                    status: [
                        { required: true, message: 'Please select a status', trigger: 'change' }
                    ],
                    sdate: [
                        { required: true, type: 'date', message: 'Please select the start-date', trigger: 'change' }
                    ],
                    edate: [
                        { required: true, type: 'date', message: 'Please select end-date', trigger: 'change' }
                    ]
                }
            }
        },
        methods: {
            handleSubmit (name) {
                this.$refs[name].validate((valid) => {

                    if (valid) {
                        this.$Message.success('Success!');
                    } else {
                        this.$Message.error('Fail!');
                    }
                })
            },

            handleReset (name) {
                this.$refs[name].resetFields();
            }
        }
    }
</script>
