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
                    <form class="col-12">
                        <div class="form">
                            <div class="form-group row">
                                <label for="name" class="col-sm-4 col-form-label"> Name </label>
                                <div class="col-sm-7">
                                  <input type="text" class="form-control" name="name" id="name" required>
                                </div>
                            </div>
                            <div class="form-group row">
                                <label for="age" class="col-sm-4 col-form-label"> Age </label>
                                <div class="col-sm-4">
                                  <input type="number" class="form-control" name="age" id="age" required>
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
                <form class="col-11">
                    <div class="form">
                        <div class="form-group row">
                            <label for="taste" class="col-sm-6 col-form-label">Do you like milk and cookies?</label>
                            <div class="custom-switch custom-switch-label-yesno">
                                <input class="custom-switch-input" id="taste" type="checkbox">
                                <label class="custom-switch-btn" for="taste"></label>
                            </div>
                        </div>
                        <div class="form-group row">
                            <label for="carol" class="col-sm-6 col-form-label">What's your favourite Christmas carol?</label>
                            <div class="col-sm-4">
                                <select class="form-control" id="carol">
                                    <option default>Choose a song</option>
                                    <option>Jingle bells</option>
                                    <option>Let it snow</option>
                                    <option>Rudolph the red nose reindeer</option>
                                    <option>The 12 days of Christmas</option>
                                    <option>We wish you a Merry Christmas</option>
                                    <option>other</option>
                                </select>
                            </div>
                        </div>
                        <div class="form-group form-group-custom">
                            <label for="help">What can you help Santa Claus with?</label>
                            <div class="row">
                                <div class="form-group col-sm-4">
                                    <div class="form-check">
                                        <input type="checkbox" class="form-check-input" id="">
                                        <label class="form-check-label" for="">Gift wrapper</label>
                                    </div>
                                    <div class="form-check">
                                        <input type="checkbox" class="form-check-input" id="">
                                        <label class="form-check-label" for="">Toy maker</label>
                                    </div>
                                    <div class="form-check">
                                        <input type="checkbox" class="form-check-input" id="">
                                        <label class="form-check-label" for="">Reindeer caretaker</label>
                                    </div>
                                </div>
                                <div class="form-group col-sm-4">
                                    <div class="form-check">
                                        <input type="checkbox" class="form-check-input" id="">
                                        <label class="form-check-label" for="">Candy maker</label>
                                    </div>
                                    <div class="form-check">
                                        <input type="checkbox" class="form-check-input" id="">
                                        <label class="form-check-label" for="">Mail sorter</label>
                                    </div>
                                    <div class="form-check">
                                        <input type="checkbox" class="form-check-input" id="">
                                        <label class="form-check-label" for="">Sleigh cleaner</label>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <!-- lights -->
                        <div class="d-flex justify-content-end">
                            <img alt="lights" src="../assets/images/lights.png" class="lights">
                        </div>
                        <!-- the end -->
                        <div class="form-group row the-end-custom">
                            <div class="col-lg-6">
                                <div class="form-group row">
                                    <label for="date" class="col-sm-4 col-form-label"> Date </label>
                                    <div class="col-sm-6">
                                        <input type="date" class="form-control" placeholder="DD.MM.YYYY" required>
                                    </div>
                                </div>
                            </div>
                            <div class="col-lg-6">
                                <label class="col-sm-6 col-form-label"> Your fingerprint </label>
                            </div>
                        </div>
                    </div>
                </form>
              </div>
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
export default {
    name: 'Form'
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
    margin-top: 2rem;
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
.elf-logo {
    width: 60%;
    position: absolute;
    top: 2rem;
    left: 3rem;
}
.decoration {
    width: 85%;
    margin: 1rem 0 1rem 4rem;
}
.elf-image {
    width: 80%;
}
.form:first-child {
    margin-top: 3rem;
}

/* lower-part main styling */
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