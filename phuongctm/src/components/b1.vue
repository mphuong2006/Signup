<script setup>
import { ref } from "vue";
const bien1 = ref([
    {
        id:1,
        tenkh:'Java',
        tengv:'Nguyễn Văn A',
        soluong:36,
        thoigian:'3 tháng',
    },
    {
        id:2,
        tenkh:'C#',
        tengv:'Nguyễn Văn B',
        soluong:32,
        thoigian:'3 tháng',
    },
    {
        id:3,
        tenkh:'Python',
        tengv:'Nguyễn Văn C',
        soluong:23,
        thoigian:'6 tháng',
    },
    {
        id:4,
        tenkh:'SQL Nâng Cao',
        tengv:'Nguyễn Văn D',
        soluong:36,
        thoigian:'9 tháng',
    },
    {
        id:5,
        tenkh:'C++',
        tengv:'Nguyễn Văn E',
        soluong:25,
        thoigian:'6 tháng',
    },
])
const bien2= ref(
    {
        id:"",
        tenkh:"",
        tengv:"",
        soluong:"",
        thoigian:"",
    }
)
const them = () =>{
    bien1.value.push({...bien2.value})
}

const xoa = (index) =>{
    bien1.value.splice(index,1)
}
</script>

<template>
     <div class="container">
     <h1 class="text-center text-danger"> Quản Lý Khóa Học</h1>
     <form class="form">
     

 <div>
   <label class="form-label fw-bold">Tên Khóa Học</label>
          <input type="text" class="w-50 form-control" v-model="bien2.tenkh" />
  </div> 
           
            <div>
         <label class="form-lable fw-bold">Thời gian học </label>
          <select class="form-select w-50 form-control" v-model="bien2.thoigian" placeholder="Trong nước">

            <option value="3 tháng">3 tháng</option>
            <option value="6 tháng">6 tháng</option>
            <option value="9 tháng">9 tháng</option>
           </select>
        </div>
        <div>
   <label class="form-label fw-bold">Tên Giảng Viên</label>
          <input type="text" class="w-50 form-control" v-model="bien2.tengv" />
  </div>
  <div>
   <label class="form-label fw-bold">Số Lượng</label>
          <input type="text" class="w-50 form-control" v-model="bien2.soluong" />
  </div>
  <button type="button" class="btn btn-primary btn-danger" @click="them"> ADD </button>

     </form>
     </div>
     <div class="mt-5">
     <div class="container">
     <table class="table table-striped table-bordered">
     <thead>
     <tr class="table-danger">
     <th>ID</th>
     <th>Tên khóa học</th>
     <th>Tên giảng viên</th>
     <th>Số Lượng</th>
     <th>Thời gian học</th>
     <th>Hành Động</th>
     </tr>
     </thead>
     <tbody>
     <tr v-for="(kh,index) in bien1" :key="kh.id" >
     <td>{{ index +1 }}</td>
     <td>{{ kh.tenkh }}</td>
     <td>{{ kh.tengv }}</td>
     <td>{{ kh.soluong}}</td>
     <td>{{ kh.thoigian }}</td>
     <td>
     <button type="button" class="btn btn-danger" @click="xoa(index)"> Xóa </button>
     </td>
     </tr>
     </tbody>
     </table>
     </div>
     </div>
   
</template>
