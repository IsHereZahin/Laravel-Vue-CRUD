<template>
  <div class="container">
    <div class="row justify-content-center">
      <div class="col-md-10">
        <h3 class="text-center text-dark mt-2" style="font-weight: 600;">Laravel 10 Vue Js Vite CRUD ( Create Read Update Delete )</h3>
      </div>
    </div>
    <div class="row">
      <!-- Form -->
      <div class="col-md-4">
        <div class="card">
          <div class="card-header text-white" style="background-color: #2F415E;">Add Record</div>
          <div class="card-body">
            <form @submit.prevent="save">
              <div class="form-group">
                <label>Student Name <span style="color: red;">*</span></label>
                <input type="text" v-model="student.name" class="form-control" placeholder="Enter Student Name" required>
              </div>
              <div class="form-group">
                <label>Student Address<span style="color: red;">*</span></label>
                <input type="text" v-model="student.address" class="form-control" placeholder="Enter Student Address" required>
              </div>
              <div class="form-group">
                <label>Student Phone</label>
                <input type="text" v-model="student.phone" class="form-control" placeholder="Enter Student Phone">
              </div>
              <button type="submit" class="btn btn-success mt-2">Save</button>
            </form>
          </div>
        </div>
      </div>
      <!-- Data Table -->
      <div class="col-md-8">
        <div class="card">
          <div class="card-header text-white" style="background-color: #2F415E;">Student List</div>
          <div class="card-body">
            <div class="table-responsive">
              <table class="table table-striped table-bordered">
                <thead class="thead-dark">
                  <tr>
                    <th scope="col">ID</th>
                    <th scope="col">Student Name</th>
                    <th scope="col">Address</th>
                    <th scope="col">Phone</th>
                    <th scope="col">Actions</th>
                  </tr>
                </thead>
                <tbody>
                  <tr v-for="student in result" :key="student.id">
                    <td>{{ student.id }}</td>
                    <td>{{ student.name }}</td>
                    <td>{{ student.address }}</td>
                    <td>{{ student.phone || 'N/A' }}</td>
                    <td>
                      <button type="button" class="btn btn-sm btn-warning" @click="edit(student)" style="margin-right: 5px;">Edit</button>
                      <button type="button" class="btn btn-sm btn-danger" @click="remove(student)">Delete</button>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import axios from 'axios';

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
        var page = "http://127.0.0.1:8000/api/student";
        axios.get(page)
        .then(
          ({ data })=>{
          console.log(data);
          this.result = data;
        })
      },
      save()
      {
        if(this.student.id == '')
        {
            this.create();
        }
        else
        {
            this.update();
        }
      },
      create()
      {
        axios.post("http://127.0.0.1:8000/api/student", this.student)
        .then(
          ({data})=>{
            alert("Record Inserted Successfully!");
            this.StudentLoad();
            this.student = {
              id: '',
              name: '',
              address: '',
              phone: ''
            }
          }
        )
      },
      edit(student)
      {
          this.student = student;
      },
      update()
      {
        var editrecords = 'http://127.0.0.1:8000/api/student/'+ this.student.id;
        axios.put(editrecords, this.student)
        .then(
          ({data})=>{
            alert("Record Updated Successfully!");
            this.StudentLoad();
            this.student = {
                id: '',
                name: '',
                address: '',
                phone: ''
              }
            }
          )
      },
      remove(student){
          var url = `http://127.0.0.1:8000/api/student/${student.id}`;
          // var url = 'http://127.0.0.1:8000/api/student/'+ student.id;
          axios.delete(url);
          alert("Record Deleted Successfully!");
          this.StudentLoad();
       }
    }
}
</script>

