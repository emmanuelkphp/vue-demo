<template>
    <main>
        <div class="container-fluid">
            <div class="row mt-2">
                <div class="col-12">
                    <div class="card card-info card-outline">
                        <div class="card-header">
                            <div class="row">
                                <div class="col-md-6">
                                    <h3 class="card-title">Students</h3>
                                </div>
                                <div class="col-md-6">
                                    <RouterLink to="" class="btn btn-sm btn-info float-end"><i class="fa fa-plus pr-1"></i> Add New</RouterLink>
                                </div>
                            </div>
                        </div>
                        <div class="card-body table-responsive">
                            <table id="contentTable" class="table table-bordered table-striped datatable-dynamic">
                                <thead>
                                    <tr>
                                        <th>#</th>
                                        <th>Title</th>
                                        <th>Action</th>
                                    </tr>
                                </thead>
                                <tbody>
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

<script>
    import axios from 'axios'

    export default {
        name: 'students',
        data(){
            return {
                students: []
            }
        },
        mounted(){
            this.getStudents();
        },
        
        methods: {
            async getStudents() {
                try {
                    const response = await axios.get('your-api-endpoint-url');
                    console.log(response.data); // Access response data
                } catch (error) {
                    console.error('Error fetching data:', error);
                }
            }
        }
    }
</script>