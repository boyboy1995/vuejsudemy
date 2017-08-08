new Vue({
  el: '#app',
  data: {
    x: 0,
    y: 0,
    count: 0,
    number:0,
    number2:0,
    name: 'type to show below!',
    title: 'hello world!',
    mylink: 'http://google.com',
    finishedLink: '<a href="http://www.google.com">Google come</a>',
    attachNavy: false,
    color: '',
    width: 100
  },
  computed: {
    output: function() {
      console.log('computed used');     //just for used function display in console log F12
      return this.number > 5 ? 'Number > 5' : 'Number <= 5'
    },
    changeColor: function() {
    	return {
      	navy: this.attachNavy,
        aqua: !this.attachNavy
      };
    },
    customStyle: function() {
      return {
        background: this.color,
        width: this.width + 'px'
      }
    }
  },
  watch: {                             // things in watch property will work upon the changes of specific property, which is 'number' for example
    number: function(value) {         // (vue auto)'value' in the function parenthesis represents changed-value of 'number'
      var numberreset = this;        // create a variable 'numberreset' to access all vue objects & functions with = this;
      setTimeout(function() {       // setTimeout(function() { numberreset.number=0;},4000);
        numberreset.number = 0;    // set a function to reset variable numberreset to 0 every 4secs (as numberreset can now access value of number)
      }, 4000);
    }
  },
  methods: {
    sayHello: function() {
      this.title = 'Hello turd!';
      return this.title;
    },
    increase: function(step, event) {
      this.count += step;
    },
    updatecoor: function(event) {
      this.x = event.clientX;
      this.y = event.clientY;
    },
    alertMe: function() {
      alert('Retard Alert!');
    },
    result: function() {
      console.log('method used');    //just for used function display in console log F12
      return this.number > 5 ? 'Greater than 5' : 'Smaller than 5'
    }
  }
});
