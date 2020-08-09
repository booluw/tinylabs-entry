<template>
  <section style="background-color: rgba($color: $baseColor, $alpha: .02);">
    <header class="header">
      <router-link to="/">
        <img src="../assets/logo.png" class="header__logo" />
      </router-link>
      <div class="pill">
        <div class="pill__img"></div>
        Hi, Joshua
        <div class="pill__rect"></div>
      </div>
    </header>
    <div class="flex-container dashboard__flex">
      <nav class="nav">
        <a href="#" class="nav__item">
          <svg width="22" height="22" viewBox="0 0 22 22" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path opacity="0.5" fill-rule="evenodd" clip-rule="evenodd" d="M8.24963 1.37544H1.37444V8.25062H8.24963V1.37544ZM8.24963 9.62506H1.37444C0.615301 9.62506 0 9.00976 0 8.25062V1.37544C0 0.6163 0.615301 0 1.37444 0H8.24963C9.00876 0 9.62506 0.6163 9.62506 1.37544V8.25062C9.62506 9.00976 9.00876 9.62506 8.24963 9.62506ZM8.24963 13.7504H1.37444V20.6256H8.24963V13.7504ZM8.24963 22H1.37444C0.615301 22 0 21.3847 0 20.6256V13.7504C0 12.9902 0.615301 12.3749 1.37444 12.3749H8.24963C9.00876 12.3749 9.62506 12.9902 9.62506 13.7504V20.6256C9.62506 21.3847 9.00876 22 8.24963 22ZM20.6246 1.37544H13.7494V8.25062H20.6246V1.37544ZM20.6246 9.62506H13.7494C12.9902 9.62506 12.3749 9.00976 12.3749 8.25062V1.37544C12.3749 0.6163 12.9902 0 13.7494 0H20.6246C21.3837 0 22 0.6163 22 1.37544V8.25062C22 9.00976 21.3837 9.62506 20.6246 9.62506ZM20.6246 13.7504H13.7494V20.6256H20.6246V13.7504ZM20.6246 22H13.7494C12.9902 22 12.3749 21.3847 12.3749 20.6256V13.7504C12.3749 12.9902 12.9902 12.3749 13.7494 12.3749H20.6246C21.3837 12.3749 22 12.9902 22 13.7504V20.6256C22 21.3847 21.3837 22 20.6246 22Z" fill="#013C61"/>
          </svg>
          <div class="mobile">Menu</div>
        </a>
        <a href="#" class="nav__item nav__item--active">
          <svg width="24" height="21" viewBox="0 0 24 21" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M17 19.3333V17.2963C17 15.0463 15.2091 13.2222 13 13.2222H5C2.79086 13.2222 1 15.0463 1 17.2963V19.3333" stroke="#2BDA53" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            <path fill-rule="evenodd" clip-rule="evenodd" d="M9 9.14815C11.2091 9.14815 13 7.32412 13 5.07407C13 2.82403 11.2091 1 9 1C6.79086 1 5 2.82403 5 5.07407C5 7.32412 6.79086 9.14815 9 9.14815Z" stroke="#2BDA53" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M23 19.3333V17.2963C22.9986 15.4397 21.765 13.8188 20 13.3546" stroke="#2BDA53" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M16 1.1324C17.7699 1.59396 19.0078 3.21832 19.0078 5.07916C19.0078 6.94 17.7699 8.56436 16 9.02592" stroke="#2BDA53" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
          <div class="mobile">Users</div>
        </a>
        <a href="#" class="nav__item">
          <svg width="24" height="18" viewBox="0 0 24 18" fill="none" xmlns="http://www.w3.org/2000/svg">
            <g opacity="0.5">
            <rect x="1" y="1" width="22" height="16" rx="2" stroke="#013C61" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M1 7H23" stroke="#013C61" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            </g>
          </svg>
          <div class="mobile">Card</div>
        </a>
      </nav>
      <div class="dashboard">
        <div class="mobile-flex">
          <h1 class="heading--sub">Employees</h1>
          <button class="btn btn--primary" @click="createEmployee()">Add New</button>
        </div>
        <div class="flex-container flex-container--space-btw flex-container--align-center dashboard__header">
          <h1 class="heading--main heading--left">Josh Bakery Ventures</h1>
          <h3 class="heading--small heading--left">62, Bode Thomas, Surulere, Lagos</h3>
        </div>
        <div class="flex-container--nopadding flex-container flex-container--space-btw flex-container--align-center">
          <div class="flex-container--nopadding flex-container flex-container--align-center flex-container--mobile-column">
            <div class="flex-container mobile-flex" style="margin: 1.2rem 0;padding: 0;">
              <select class="selector" v-model="employee.role">
                <option>Change Role</option>
                <option value="Admin">Admin</option>
                <option value="User">User</option>
              </select>
              <button class="btn" @click="updateEmployee()">Change</button>
            </div>
            <div class="input-group__sub-group input-group__sub-group--border" style="border-radius: .2rem;padding: 1rem 1rem;align-items: center;">
              <input id="search" type="search" class="input-group__input" placeholder="Enter staff name here" v-model="searchParams" @keyup="filterRows()"/>
              <svg width="15" height="16" viewBox="0 0 15 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd" d="M6.05556 11.6555C8.84766 11.6555 11.1111 9.3921 11.1111 6.59999C11.1111 3.80788 8.84766 1.54443 6.05556 1.54443C3.26345 1.54443 1 3.80788 1 6.59999C1 9.3921 3.26345 11.6555 6.05556 11.6555Z" stroke="#6A7E8A" stroke-width="1.2" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M14.2611 15.1167L9.55555 10.3333" stroke="#6A7E8A" stroke-width="1.2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </div>
          </div>
          <div class="pagination">
            <div class="pagination__active-page">1</div>
            of 2
            <div class="pagination__btns">
              <span class="pagination__btn">
                <svg width="5" height="8" viewBox="0 0 5 8" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M3.85114 0.829544L0.631438 4.04924L3.85114 7.26894" stroke="white" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </span>
              <span class="pagination__btn">
                <svg width="5" height="8" viewBox="0 0 5 8" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M1.05945 0.829544L4.27915 4.04924L1.05945 7.26894" stroke="white" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </span>
            </div>
          </div>
        </div>
        <div class="responsive-table">
          <table class="dashboard__table" ref="table">
            <tr class="table__header">
              <th>
                <span class="square-box"></span>
              </th>
              <th>first name</th>
              <th>last name</th>
              <th>email</th>
              <th>phone</th>
              <th>role</th>
              <th style="color: transparent;">
                Delete
              </th>
            </tr>
            <tr v-for="data in dummyEmployee" :key="data._id">
              <td>
                <input type="radio" name="employee" class="checkbox" :id="data._id" />
                <label :for="data._id" class="square-box"  @click="changeDefault(data)"></label>
              </td>
              <td>{{data.firstname}}</td>
              <td>{{data.lastname}}</td>
              <td>{{data.email}}</td>
              <td>{{data.phone}}</td>
              <td>{{data.role}}</td>
              <td>
                <svg class="delete__btn" width="18" height="21" viewBox="0 0 18 21" fill="none" xmlns="http://www.w3.org/2000/svg" @click="deleteEmployee(data._id)">
                  <path d="M1 5.55555H2.77778H17" stroke="#6A7E8A" stroke-width="1.2" stroke-linecap="round" stroke-linejoin="round"/>
                  <path d="M3.9778 5.55555C3.9778 4.89281 3.44054 4.35555 2.7778 4.35555V5.55555H3.9778ZM3.9778 18V5.55555H2.7778V18H3.9778ZM4.55557 18.5778C4.23647 18.5778 3.9778 18.3191 3.9778 18H2.7778C2.7778 18.9818 3.57373 19.7778 4.55557 19.7778V18.5778ZM13.4445 18.5778H4.55557V19.7778H13.4445V18.5778ZM14.0222 18C14.0222 18.3191 13.7636 18.5778 13.4445 18.5778V19.7778C14.4263 19.7778 15.2222 18.9818 15.2222 18H14.0222ZM14.0222 5.55555V18H15.2222V5.55555H14.0222ZM15.2222 4.35555C14.5595 4.35555 14.0222 4.89281 14.0222 5.55555H15.2222H15.2222V4.35555ZM16.4222 5.55555C16.4222 4.89281 15.885 4.35555 15.2222 4.35555V5.55555H16.4222ZM16.4222 18V5.55555H15.2222V18H16.4222ZM13.4445 20.9778C15.089 20.9778 16.4222 19.6446 16.4222 18H15.2222C15.2222 18.9818 14.4263 19.7778 13.4445 19.7778V20.9778ZM4.55557 20.9778H13.4445V19.7778H4.55557V20.9778ZM1.5778 18C1.5778 19.6446 2.91099 20.9778 4.55557 20.9778V19.7778C3.57373 19.7778 2.7778 18.9818 2.7778 18H1.5778ZM1.5778 5.55555V18H2.7778V5.55555H1.5778ZM2.7778 4.35555C2.11505 4.35555 1.5778 4.89281 1.5778 5.55555H2.7778V4.35555ZM6.64446 3.77777C6.64446 3.45867 6.90314 3.19999 7.22224 3.19999V1.99999C6.2404 1.99999 5.44446 2.79593 5.44446 3.77777H6.64446ZM6.64446 5.55555V3.77777H5.44446V5.55555H6.64446ZM5.44446 6.75555C6.1072 6.75555 6.64446 6.21829 6.64446 5.55555H5.44446V6.75555ZM4.24446 5.55555C4.24446 6.21829 4.78172 6.75555 5.44446 6.75555V5.55555H4.24446ZM4.24446 3.77777V5.55555H5.44446V3.77777H4.24446ZM7.22224 0.799994C5.57766 0.799994 4.24446 2.13319 4.24446 3.77777H5.44446C5.44446 2.79593 6.2404 1.99999 7.22224 1.99999V0.799994ZM10.7778 0.799994H7.22224V1.99999H10.7778V0.799994ZM13.7556 3.77777C13.7556 2.13319 12.4224 0.799994 10.7778 0.799994V1.99999C11.7596 1.99999 12.5556 2.79593 12.5556 3.77777H13.7556ZM13.7556 5.55555V3.77777H12.5556V5.55555H13.7556ZM12.5556 6.75555C13.2183 6.75555 13.7556 6.21829 13.7556 5.55555H12.5556V6.75555ZM11.3556 5.55555C11.3556 6.21829 11.8928 6.75555 12.5556 6.75555V5.55555H11.3556ZM11.3556 3.77777V5.55555H12.5556V3.77777H11.3556ZM10.7778 3.19999C11.0969 3.19999 11.3556 3.45867 11.3556 3.77777H12.5556C12.5556 2.79593 11.7596 1.99999 10.7778 1.99999V3.19999ZM7.22224 3.19999H10.7778V1.99999H7.22224V3.19999Z" fill="#6A7E8A"/>
                  <path d="M7.22222 9.99999V15.3333" stroke="#6A7E8A" stroke-width="1.2" stroke-linecap="square" stroke-linejoin="round"/>
                  <path d="M10.7778 9.99999V15.3333" stroke="#6A7E8A" stroke-width="1.2" stroke-linecap="square" stroke-linejoin="round"/>
                </svg>
              </td>
            </tr>
          </table>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Dashboard',
  data() {
    return {
      checkbox: false,
      employees: [],
      employee: {},
      apiURL: 'https://crudcrud.com/api/1e0110dfc9ea4e2b82031014edab66d5',
      searchParams: '',
      dummyEmployee: [
        {
          _id: 984938,
          firstname: 'Jack',
          lastname: 'Doe',
          phone: '9902883839',
          role: 'Admin',
          email: 'janetdoe@dummies.com'
        },
        {
          _id: 98499009,
          firstname: 'Jack',
          lastname: 'Doe',
          phone: '9902883839',
          role: 'Admin',
          email: 'janetdoe@dummies.com'
        },
        {
          _id: 984938777,
          firstname: 'Jack',
          lastname: 'Doe',
          phone: '9902883839',
          role: 'Admin',
          email: 'janetdoe@dummies.com'
        }
      ]
    }
  },
  methods: {
    changeDefault: function(payload) {
      this.employee = payload;
    },
    createEmployee: function() {
      let employee = {
        firstname: 'Janet',
        lastname: 'Doe',
        email: 'janetDoe@dummies.com',
        phone: '0988883904',
        role: 'Admin'
      }
      axios.post(`https://cors-anywhere.herokuapp.com/${this.apiURL}/employees`, employee,{
        headers: {
          //'Content-Type': 'application/json',
          'Access-Control-Allow-Origin': '*'
        }
      }).then( response =>{
        alert("New Employee added")
        console.log(response.data)
      }).catch(error => {
        console.log(error)
        alert("An error occured")
      })
    },
    fetchEmployees: function() {
      axios.get(`https://cors-anywhere.herokuapp.com/${this.apiURL}/employees`,{
        headers: {
          //'Content-Type': 'application/json',
          'Access-Control-Allow-Origin': '*'
        }
      }).then( result => {
        this.employees = result.data
      })
    },
    updateEmployee: function() {
      axios.put(`https://cors-anywhere.herokuapp.com/${this.apiURL}/employees/${this.employee._id}`, this.employee,{
        headers: {
          //'Content-Type': 'application/json',
          'Access-Control-Allow-Origin': '*'
        }
      }).then(() => {
        this.employee = {}
        alert("User's role has been changed successfully")
      }).catch( error=> {
        console.log(error)
        alert("An error occured.")
      })
    },
    deleteEmployee: function(payload) {
      axios.delete(`https://cors-anywhere.herokuapp.com/${this.apiURL}/${payload}`,
      {
        headers: {
          'Access-Control-Allow-Origin': '*'
        }
      }).then(() => {
        console.log("Delete Employee's data")
      }).catch(error => {
        console.log(error)
        alert("An error occured.")
      })
    },
    filterRows: function() {
      let tr = this.$refs.table.getElementsByTagName('tr')
      for (let i = 0; i < tr.length; i++) {
        let td = tr[i].getElementsByTagName("td")[1];
        if (td) {
          let txtValue = td.textContent || td.innerText;
          if(txtValue.toUpperCase().indexOf(this.searchParams.toUpperCase()) > -1) {
            tr[i].style.display = "";
          } else {
            tr[i].style.display = "none"
          }
        }
      }
    }
  },
  mounted() {
    this.fetchEmployees()
  },
}
</script>

<style lang="scss">
$background: #E5E5E5;
$baseColor: #2BDA53;
$textColor: #013C61;
$colorFaint: #6A7E8A;
$boxShadowLogin: 0px 20px 50px #EAEEE9;
$borderRadius: 5px;
$boxShadow: 0px 7px 15px rgba(43, 218, 83, 0.2);
$border: 1px solid #E6E7EB;
$mainHeader: 36px;
$subHeader: 26px;
$thirdHeader: 22px;
$input: 20px;


.header {
  position: relative;
  background-color: white;
  display: flex;
  justify-content: space-between;
  padding: .5rem .7rem .5rem .2rem;
  border: 1px solid rgba(106, 126, 138, 0.1);
  &__logo {
    height: 3rem;
  }
}
.pill {
  display: flex;
  align-items: center;
  font-weight: 700;
  &__img {
    padding: .8rem .8rem;
    border-radius: 50%;
    background-color: #6A7E8A;
    margin: 0 .3rem;
  }
  &__rect {
    margin: .7rem 0 0 .4rem;
    height: 1rem;
    width: 1rem;
    background-color: transparent;
    border: .5rem solid transparent;
    border-top-color: black;
  }
}
.nav {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  width: auto;
  padding: 0;
  &__item {
    background-color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 1rem .5rem;
    margin: 0;
    border-radius: $borderRadius;
    border-bottom: .3rem solid transparent;
    transition: .3s ease-in;
    &:hover, &--active {
      border-color: $baseColor;
      svg {
        stroke: $baseColor;
        opacity: 1;
      }
    }
  }
}
.mobile {
  display: block;
  margin: 0 .4rem;
  color: $colorFaint; 
}
.selector {
  padding: .5rem .5rem;
  margin: 0 1rem 0 0;
  width: 20rem;
  border: 1px solid rgba(106, 126, 138, 0.4);
  box-sizing: border-box;
  border-radius: 3px;
  background-color: white;
  cursor: pointer;
  outline: none;
}
.pagination {
  display: flex;
  margin: 2rem 0;
  justify-content: flex-end;
  &__active-page {
    border-radius: 3px;
    padding: 0 .3rem;
    margin: 0 .3rem 0 0;
    border: 1px solid rgba(1, 60, 97, 0.1);
  }
  &__btn {
    display: inline-flex;
    justify-content: center;
    align-items: center;
    background-color: $baseColor;
    padding: .4rem .5rem;
    border-radius: 50%;
    margin: 0 0 0 .3rem;
    cursor: pointer;
  }
}
.dashboard__header {
   background-color: white;
   padding: .1rem 1.8rem 1.8rem;
   border-radius: 5px;
}
.dashboard__table {
  border-spacing: 0 1rem;
  width: 100%;
  color: $textColor;
  .table__header {
    text-transform: uppercase;
  }
  th {
    padding: .7rem 1rem;
    width: 20%;
  }
  th:last-of-type, th:first-of-type {
    width: 10%;
  }
  td {
    padding: 1.2rem 1.3rem;
    width: 15%;
  }
  .checkbox {
    display: none;
    &:checked ~ .square-box, .square-box {
      background-color: $baseColor;
    }
  }
  .square-box {
      display: inline-block;
      padding: .5rem .5rem;
      border: 2px solid rgba(1, 60, 97, 0.1);
      cursor: pointer;
    }
}
.responsive-table {
  margin: 2rem 0 0;
  overflow-x: auto;
}
.data {
  margin: 20rem;
}
td {
  margin: .3rem 0;
  height: 3rem;
  padding: 1rem 1rem;
  background-color: white;
}
  td:first-child {
    border-radius: 5px 0 0 5px;
    width: 2rem;
  }
  td:last-child {
    border-radius: 0 5px 5px 0;
  }
  .delete__btn {
    cursor: pointer;
  }
@media (min-width: 1200px) {
  .header {
    padding: 1rem 3.5rem 1rem 1rem;
  }
  .nav {
    display: inline-flex;
    flex-direction: column;
    justify-content: flex-start;
    padding: 2.5rem 0 0;
    margin: 0;
    background-color: white;
    border: 1px solid rgba(106, 126, 138, 0.1);
    &__item {
      padding: .8rem 1.6rem .8rem 1.3rem;
      margin: 2rem 0;
      border: none;
      border-radius: 0;
      border-left: .3rem solid transparent;
      transition: .3s ease-in;
      &:hover, &--active {
        border-color: $baseColor;
        svg {
          stroke: $baseColor;
          opacity: 1;
        }
      }
    }
  }
  .dashboard {
    margin: 3.5rem 3.5rem 0;
    text-align: justify;
    flex-basis: 100%;
  }
  .dashboard__flex {height: 100%;}
  .mobile {display: none;}
}
</style>