<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-10">
                <h3 class="text-center text-dark mt-2">Laravel 10 Vue Js Vite CRUD ( Create Read Update Delete )</h3>
            </div>
        </div>
        <div class="row">
            <div class="col-md-4">
                <div class="card-header">
                    Add Record
                </div>
                <div class="card-body">
                    <form>

                    <div class="form-group">
                        <label>Student name</label>
                        <input type="text" name="student.name" class="form-control"  placeholder="Student name">

                    </div>
                    <div class="form-group">
                        <label>Student Address</label>
                        <input type="text" name="student.address" class="form-control"  placeholder="Student Address">

                    </div>

                    <div class="form-group">
                        <label>Phone</label>
                        <input type="text" name="student.phone" class="form-control"  placeholder="Phone">

                    </div>

                    <button type="submit" class="btn btn-primary">Save</button>
                    </form>
                </div>
            </div>
            <div class="col-md-8">
                <h2>Student List</h2>
                <table class="table table-dark">
                    <thead>
                        <tr>
                        <th scope="col">ID</th>
                        <th scope="col">Student Name</th>
                        <th scope="col">Address</th>
                        <th scope="col">Phone</th>
                        <th scope="col">Option</th>
                        </tr>
                    </thead>
                </table>
            </div>
        </div>
    </div>
</template>
<script>
export default{
    name: 'Student',
    data() {
        return {
            result: {},
            student: {
                id: '',
                name: '',
                address: '',
                phone: ''
            }
        }
    },

    created()
    {
        this.StudentLoad();
    },
    mounted()
    {
        console.log("mounted() called.......");
    },

    methods:
    {
        StudentLoad ()
        {
            
        },
    }
}
</script>

