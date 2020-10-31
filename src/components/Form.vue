<template>
  <div class="A4">
      <div class="header row">
          <div class="header-milk col-lg-3"></div>
          <div class="header-pink col-lg-3"></div>
          <div class="header-blue col-lg-6"></div>
      </div>
      <div class="main">
          <div class="upper-part row">
                <div class="col-lg-6">
                    <div class="title-wrap">
                        <img alt="elf-logo" src="../assets/images/elf-logo.png" class="elf-logo">
                        <h1> application </h1>
                    </div>
                    <form action="">
                        <div class="form">
                            <div class="col-lg-8">
                                <label> Name </label>
                                <input type="text" class="form-control" required>
                            </div>
                            <div class="col-lg-8">
                                <label> Age </label> 
                                <input type="text" class="form-control" required>
                            </div>
                        </div>
                    </form>
                </div>
                <div class="col-lg-6">
                    <img alt="elf-image" src="../assets/images/elf-image.png" class="elf-image">
                </div>
          </div>
          <div class="lower-part row">
              <form action="">
                <div>
                    <label>Do you like milk and cookies?</label>
                    <div class="custom-switch custom-switch-label-yesno">
                        <input class="custom-switch-input" id="example_3" type="checkbox">
                        <label class="custom-switch-btn" for="example_3"></label>
                    </div>
                </div>
                <div class="form-group">
                    <label for="exampleFormControlSelect1">What is you favourite Christmas carol?</label>
                    <select class="form-control" id="exampleFormControlSelect1">
                        <option default>Choose a song</option>
                        <option>1</option>
                        <option>2</option>
                        <option>3</option>
                        <option>4</option>
                        <option>5</option>
                        <option>other</option>
                    </select>
                    <p>Which one?</p>
                </div>
                <div class="form-group">
                    <label for="exampleFormControlSelect1">What can you help Santa Claus with?</label>
                    <div class="form-check">
                        <input type="checkbox" class="form-check-input" id="">
                        <label class="form-check-label" for="">Gift wrapper</label>
                    </div><div class="form-check">
                        <input type="checkbox" class="form-check-input" id="">
                        <label class="form-check-label" for="">Toy maker</label>
                    </div>
                    <div class="form-check">
                        <input type="checkbox" class="form-check-input" id="">
                        <label class="form-check-label" for="">Reindeer caretaker</label>
                    </div>
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
                <div class="col-lg-8">
                    <label> Date </label>
                    <input type="text" class="form-control" placeholder="DD.MM.YYYY" required>
                </div>
                <div class="col-lg-8">
                    <label> Your fingerprint </label>
                </div>
              </form>
          </div>
      </div>
      <div class="footer">

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
.row {
    margin: 0;
}
.header-milk {
    background-color: #f3e0c2;
}
.header-pink {
    background-color: #b14f4c;
}
.header-blue {
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
.title-wrap h1 {
    margin-top: 8rem;
    text-align: right;
}
.elf-logo {
    width: 60%;
    position: absolute;
    top: 0;
    left: 3rem;
}
.elf-image {
    width: 80%;
}
.form:first-child {
    margin-top: 3rem;
}

/* lower-part main styling */


</style>