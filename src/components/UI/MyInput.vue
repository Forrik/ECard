<template>
    <div class="group">      
        <input :value="value" @input="updateInput" class="input" type="text" required>
        <span class="bar"></span>
       
      </div>
</template>

<script>
    export default {
        name: 'my-input',
        props: {
            value: [String, Number]
        },
        methods: {
            updateInput(event) {
                this.$emit('update:value', event.target.value)
            }
        }
    }
</script>

<style scoped>
.group 			  { 
    position:relative; 
   
  }

  .input {
    font-size:18px;
    padding: 10px 10px 1px 5px;
    display:block;
    width:300px;
    border:none;
    border-bottom:1px solid #757575;
    background-color: transparent;
  }
  .input:focus { 
    outline:none; 
}

.input::placeholder {
    color:#999; 
  font-size:18px;
  font-weight:normal;
  position:absolute;
  pointer-events:none;
  left:5px;
  top:10px;
  transition:0.2s ease all; 
  -moz-transition:0.2s ease all; 
  -webkit-transition:0.2s ease all;
}

.input:focus ~ .input__value, .input:valid ~ .input__value 		{
  
  }
  
  .input::placeholder:focus {
    top:-20px;
    font-size:14px;
    color:#5264AE;
  }

.bar { 
    position:relative; 
    display:block;
    width:300px; 
    }
.bar:before, .bar:after {
  content:'';
  height:2px; 
  width:0;
  bottom:1px; 
  position:absolute;
  background:#5264AE; 
  transition:0.2s ease all; 
  -moz-transition:0.2s ease all; 
  -webkit-transition:0.2s ease all;
}
.bar:before {
  left:50%;
}
.bar:after {
  right:50%; 
}

.input:focus ~ .bar:before, .input:focus ~ .bar:after {
  width:50%;
}

</style>