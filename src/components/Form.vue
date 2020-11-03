<template>
  <div class="A4">
      <div class="header row row-custom">
          <div class="colour-milk col-lg-3"></div>
          <div class="colour-red col-lg-3"></div>
          <div class="colour-green col-lg-6"></div>
      </div>
      <div class="main">
          <!-- Upper-part -->
          <div class="upper-part row">
                <div class="col-lg-6 upper-part-left-wrap">
                    <div class="title-wrap">
                        <img alt="elf-logo" src="../assets/images/elf-logo.png" class="elf-logo">
                        <h1> application </h1>
                    </div>
                    <form class="col-12" @submit.prevent="submit">
                        <div class="form form-custom-height">
                            <div class="form-group row adjust-height">
                                <label class="col-sm-4 col-form-label"> Name </label>
                                <div class="col-sm-7" v-if="!submitStatus">
                                  <input type="text" class="form-control" name="name"
                                  autocomplete="off"
                                  v-model.trim="name"
                                  :class="{ 'is-invalid': $v.name.$error }"
                                  >
                                  <!-- If you want a real-time update on validation, then use this version: -->
                                  <!-- v-model.trim="$v.name.$model" -->
                                  <!-- If you want to show css styling for 'is-valid' validation: -->
                                  <!-- :class="{ 'is-invalid': $v.name.$error, 'is-valid': !$v.name.$invalid }" -->
                                  <div class="invalid-feedback d-block">
                                    <span v-if="!$v.name.required && $v.name.$dirty && !submitStatus">Name is required</span>
                                    <span v-if="!$v.name.minLength && $v.name.$dirty && !submitStatus">Name must have at least {{$v.name.$params.minLength.min}} letters.</span>
                                    <span v-if="!$v.name.alpha && $v.name.$dirty && $v.name.minLength && !submitStatus">Use only alphabetic characters</span>
                                  </div>
                                </div>
                                <div class="col-sm-7 col-form-label" v-if="submitStatus">
                                    <strong>{{name}}</strong>
                                </div>
                            </div>
                            <div class="form-group row">
                                <label class="col-sm-4 col-form-label"> Age </label>
                                <div class="col-sm-7" v-if="!submitStatus">
                                    <div class="col-sm-6 col-sm-6-custom">
                                    <input type="number" class="form-control" name="age"
                                    autocomplete="off"
                                    v-model.trim="age" 
                                    :class="{ 'is-invalid': $v.age.$error }"
                                    >
                                    </div>
                                    <div class="invalid-feedback d-block">
                                        <span v-if="!$v.age.between && $v.age.$dirty && !submitStatus">Must be at least {{$v.age.$params.between.min}} y.o.</span>
                                    </div>
                                </div>
                                <div class="col-sm-7 col-form-label" v-if="submitStatus">
                                    <strong>{{age}}</strong>
                                </div>
                            </div>
                        </div>
                    </form>
                    <img alt="decoration" src="../assets/images/decoration.png" class="decoration">
                </div>
                <div class="col-lg-6">
                    <img alt="elf-image" src="../assets/images/elf-image.png" class="elf-image">
                </div>
          </div>
          <!-- Lower-part -->
          <div class="lower-part row">
              <div class="col-lg-12">
                <form class="col-11" @submit.prevent="submit">
                    <div class="form form-custom">
                        <div class="form-group row">
                            <label for="taste" class="col-sm-6 col-form-label">Do you like milk and cookies?</label>
                            <div class="custom-switch custom-switch-label-yesno" v-if="!submitStatus">
                                <input class="custom-switch-input" id="taste" type="checkbox" v-model="yes">
                                <label class="custom-switch-btn" for="taste"></label>
                            </div>
                            <div class="col-sm-4 col-form-label" v-if="submitStatus">
                                <strong>{{yes ? "Yes" : "No"}}</strong>
                            </div>
                        </div>
                        <div class="form-group row">
                            <label for="carol" class="col-sm-6 col-form-label">What's your favourite Christmas carol?</label>
                            <div class="col-sm-5" v-if="!submitStatus">
                                <select class="form-control" id="carol" v-model="carol">
                                    <option default disabled value="">Choose a song</option>
                                    <option>Jingle bells</option>
                                    <option>Let it snow</option>
                                    <option>Rudolph the red nose reindeer</option>
                                    <option>The 12 days of Christmas</option>
                                    <option>We wish you a Merry Christmas</option>
                                    <option>other</option>
                                </select>
                            </div>
                            <div class="col-sm-5 col-form-label" v-if="submitStatus">
                                <strong>{{carol}}</strong>
                            </div>
                        </div>
                        <div class="form-group row" v-if="carol === 'other' ? isHidden === true : isHidden === false">
                            <label for="taste" class="col-sm-6 col-form-label">*If other, what is the carol's name?</label>
                            <div class="col-sm-4" v-if="!submitStatus">
                                <input type="text" class="form-control" name="carol-name" id="carol-name" 
                                autocomplete="off"
                                v-model.trim="other"
                                >
                                <div class="invalid-feedback d-block" v-if="!submitStatus">
                                    <span v-if="!$v.other.maxLength && $v.other.$dirty && !submitStatus">Must not have more than {{$v.other.$params.maxLength.max}} letters.</span>
                                </div>
                            </div>
                            <div class="col-sm-5 col-form-label" v-if="submitStatus">
                                <strong>{{other}}</strong>
                            </div>
                        </div>
                        <div class="form-group form-group-custom">
                            <label for="help">What can you help Santa Claus with?</label>
                            <div class="row">
                                <div class="form-group col-sm-4">
                                    <div class="form-check">
                                        <input type="checkbox" class="form-check-input" value="Gift wrapper" id="gift" 
                                        v-model="checkedJobs"
                                        :disabled="submitStatus"
                                        >
                                        <span>
                                            <label class="form-check-label" for="gift">Gift wrapper</label>
                                        </span>
                                    </div>
                                    <div class="form-check">
                                        <input type="checkbox" class="form-check-input" value="Toy maker" id="toy" 
                                        v-model="checkedJobs"
                                        :disabled="submitStatus"
                                        >
                                        <span>
                                            <label class="form-check-label" for="toy">Toy maker</label>
                                        </span>
                                    </div>
                                    <div class="form-check">
                                        <input type="checkbox" class="form-check-input" value="Reindeer caretaker" id="caretaker" 
                                        v-model="checkedJobs"
                                        :disabled="submitStatus"
                                        >
                                        <span>
                                            <label class="form-check-label" for="caretaker">Reindeer caretaker</label>
                                        </span>
                                    </div>
                                </div>
                                <div class="form-group col-sm-4">
                                    <div class="form-check">
                                        <input type="checkbox" class="form-check-input" value="Candy maker" id="candy" 
                                        v-model="checkedJobs"
                                        :disabled="submitStatus"
                                        >
                                        <span>
                                            <label class="form-check-label" for="candy">Candy maker</label>
                                        </span>
                                    </div>
                                    <div class="form-check">
                                        <input type="checkbox" class="form-check-input" value="Mail sorter" id="mail" 
                                        v-model="checkedJobs"
                                        :disabled="submitStatus"
                                        >
                                        <span>
                                            <label class="form-check-label" for="mail">Mail sorter</label>
                                        </span>
                                    </div>
                                    <div class="form-check">
                                        <input type="checkbox" class="form-check-input" value="Sleigh cleaner" id="cleaner" 
                                        v-model="checkedJobs"
                                        :disabled="submitStatus"
                                        >
                                        <span>
                                            <label class="form-check-label" for="cleaner">Sleigh cleaner</label>
                                        </span>
                                    </div>
                                </div>
                                <!-- different approach to handle array -->
                                <!-- <div class="form-group col-sm-4">
                                    <div class="form-check" v-for="job in jobList.slice(0,3)" :key="job">
                                        <input type="checkbox" class="form-check-input" :value="job" id="gift" v-model="checkedJobs">
                                        <label class="form-check-label" for="gift">{{job}}</label>
                                    </div>                                    
                                </div>
                                <div class="form-group col-sm-4">
                                    <div class="form-check" v-for="job in jobList.slice(3,6)" :key="job">
                                        <input type="checkbox" class="form-check-input" :value="job" id="gift" v-model="checkedJobs">
                                        <label class="form-check-label" for="gift">{{job}}</label>
                                    </div>                                    
                                </div> -->
                            </div>
                        </div>
                        <!-- lights-decoration -->
                        <div class="d-flex justify-content-end">
                            <img alt="lights" src="../assets/images/lights.png" class="lights">
                        </div>
                        <!-- the end -->
                        <div class="form-group row the-end-custom">
                            <div class="col-lg-6">
                                <div class="form-group row">
                                    <label for="date" class="col-sm-4 col-form-label"> Date </label>
                                    <div class="col-sm-7" v-if="!submitStatus">
                                        <input type="date" class="form-control" name="date" placeholder="DD.MM.YYYY"
                                        ref="pastDate"
                                        v-model.trim="date"
                                        :class="{ 'is-invalid': $v.date.$error }"
                                        >
                                        <div class="invalid-feedback d-block">
                                            <span v-if="!$v.date.required && $v.date.$dirty && !submitStatus">Field is required</span>
                                        </div>
                                    </div>
                                    <div class="col-sm-7 col-form-label" v-if="submitStatus">
                                        <strong>{{dateCustom}}</strong>
                                    </div>
                                </div>
                            </div>
                            <div class="col-lg-6">
                                <label class="col-sm-7 col-form-label"> Your fingerprint:
                                        <div class="tooltipCustom">
                                            <sup>
                                                <i class="fas fa-info-circle fas-custom"></i> 
                                            </sup>
                                            <span class="tooltiptext">Print out the application and then put your fingerprint</span>
                                        </div> 
                                </label>
                            </div>
                        </div>
                    </div>
                </form>
              </div>
          </div>
      </div>
      <!-- submit button -->
      <div class="col-11 col-11-custom">
            <div class="d-flex justify-content-center" v-if="!submitStatus">
                <button type="submit" class="btn" @click="submit()">Submit</button>
            </div>
      </div>
      <div class="footer row row-custom">
            <div class="colour-green col-lg-6"></div>
            <div class="colour-red col-lg-3"></div>
            <div class="colour-milk col-lg-3">
                <div class="row h-100">
                    <div class="footer-date col-sm-12 my-auto">
                        <div> © {{ new Date().getFullYear() }} - SmileyDoodle </div>
                    </div>
                </div>
            </div>
      </div>
  </div>
</template>

<script>
import { required, minLength, maxLength, alpha, between } from 'vuelidate/lib/validators';
import moment from 'moment';

export default {
    name: 'Form',
    data() {
        return {
            isHidden: true,
            name: '',
            age: 0,
            yes: false,
            carol: '',
            other: '',
            date: '',
            checkedJobs: [],
            submitStatus: null,
            // jobList: [
            //     'Gift wrapper',
            //     'Toy maker',
            //     'Reindeer caretaker',
            //     'Candy maker',
            //     'Mail sorter',
            //     'Sleigh cleaner'
            // ] // different approach to handle array
        }
    },
    computed: {
        dateCustom: function() {
            var dateCustom = moment(this.date).format('MMM Do YYYY');
            return dateCustom;
        }
    },
    validations: {
        name: {
        required,
        alpha,
            minLength: minLength(3)
        },
        age: {
        required,
            between: between(3, 100)
        },
        other: {
        alpha,
            maxLength: maxLength(30)
        },
        date: {
        required
        }
    },
    methods: {
        submit() {
            // console.log('submit!')
            this.$v.$touch()
            if (!this.$v.$invalid) { //if it's valid
                this.submitStatus = true
                console.log("submitStatus", this.submitStatus)
            } else {
                this.submitStatus = false
                console.log("submitStatus", this.submitStatus)
            }
        }
    },
    mounted() {
        var today = new Date().toISOString().split('T')[0];
        this.$refs.pastDate.setAttribute('min', today);
    }
}
</script>

<style>
@import '../assets/css/component-custom-switch.min.css';

.A4 {
    position: relative;
    width: 21cm;
    height: 29.7cm; 
    background: white;
    display: block;
    margin: 0 auto;
    margin-bottom: 0.5cm;
    box-shadow: 0 0 0.5cm rgba(0,0,0,0.5);
}
.fas-custom {
    font-size: 14px;
    cursor: pointer;
    opacity: 0.3;
}
.invalid-feedback {
    font-size: 60%;
}
input[type="checkbox"][disabled]:checked ~ span {
  color: #212520;
  font-weight: bold;
}

/* header styling */
.header {
    height: 30px;
}
.row-custom {
    margin: 0;
}
.colour-milk {
    background-color: #f3e0c2;
}
.colour-red {
    background-color: #b14f4c;
}
.colour-green {
    background-color: #4b7768;
}

/* main styling */
.main {
    margin-top: 1rem;
}
form {
    text-align: left;
    margin-left: 3rem;
}

/* upper-part main styling */
.upper-part-left-wrap {
    padding-top: 2rem;
}
.title-wrap h1 {
    margin-top: 8rem;
    text-align: right;
}
.col-sm-6-custom {
    padding: 0;
}
.elf-logo {
    width: 60%;
    position: absolute;
    top: 2rem;
    left: 3rem;
}
.decoration {
    width: 85%;
    margin: 0 0 1rem 4rem;
}
.elf-image {
    width: 80%;
}
.form:first-child {
    margin-top: 2rem;
}
.form-custom-height {
    height: 140px;
}
.adjust-height {
    height: 50px;
}

/* lower-part main styling */
.form-custom {
    margin-top: 1rem !important;
}
.custom-switch {
    padding-left: 15px;
}
.form-group-custom {
    margin-bottom: 0;
}
.lights {
    width: 50%;
    margin-right: 2.5rem;
}
.the-end-custom {
    margin-top: 2rem;
    margin-bottom: 0;
}
.col-11-custom {
    margin-left: 2rem;
    position: absolute;
    bottom: 50px;
}
.btn {
    background-color: #4b7768;
    color: #fff;
    margin-top: 0.5rem;
    box-shadow: 0 0.5em 1em -0.125em rgba(10,10,10,.1), 0 0 0 0 rgba(10,10,10,.02);
}

/* Tooltip container */
.tooltipCustom {
  position: relative;
  display: inline-block;
}
/* Tooltip text */
.tooltipCustom .tooltiptext {
  visibility: hidden;
  width: 210px;
  background-color: #f3e0c2;
  opacity: 0.9;
  color: #212520;
  font-size: 14px;
  text-align: center;
  padding: 7px 14px;
  border-radius: 6px;
  /* Position the tooltip text - see examples below! */
  position: absolute;
  z-index: 1;
  bottom: 110%;
  left: 50%;
  margin-left: -90px;
}
/* Show the tooltip text when you mouse over the tooltip container */
.tooltipCustom:hover .tooltiptext {
  visibility: visible;
}

/* footer styling */
.footer {
    position: absolute;
    bottom: 0;
    height: 30px;
    width: 100%;
}
.footer-date {
    font-size: 10px;
}
</style>