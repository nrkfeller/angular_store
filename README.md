# Angular tutorial

## functions as abstractions

Functions can be passed other functions. This allows for validation that a function is working
a function can prevent another function of executing if there is a hazard

    var work = function() {
      
      console.log("learning JS");
    };
    
    var dowork = function(f) {
      console.log("start work");
      
      try {
        f()
      }
      catch(ex){
        console.log(ex);
      }
      console.log("ended work");
    };
    
    dowork(work);
    
## Using objects

    var createWorker = function(){
      
      var workCount = 0;
      
      var task1 = function(){
        workCount += 1;
        console.log("task1 " + workCount);
      }
      var task2 = function(){
        workCount += 1;
        console.log("task2 " + workCount);
      }
      return {
        job1: task1,
        job2: task2
      }
    }
    
    var worker = createWorker();
    
    worker.job1();
    worker.job2();

## Avoiding global variables
How can we prevent global variables from existing, wrap it all within a program

    var program = funtion(){
      all code
    }

or even better create an immediately invoked function

    (function() {
      all code
    }());


## Controller basics

* ng-controller, is a directive. we can place it inside a div like so <div ng-controller='MainController'>
    var MainController = function($scope){
        $scope.message = "hello";
    };

## Angular directives
    ng-app -- ng-app='appname
    ng-controller -- ng-controller='PotatoController as potato'
    ng-class -- ng-class="{ active: tab.isSet(3) }"
    ng-show -- ng-show='store.product.soldOut'
    ng-hide -- ng-hide='store.product.available'
    ng-repeat -- ng-repeat='element in bag.elementlist'
    ng-src -- ng-src="{{ product.images[0].full }}" />
    ng-click -- ng-click="tab.setTab(3)"
    

## Angular filters
    {{ data | filer:options }}
    
    {{ '41235345324' | date:'mm/dd/yyyy' }}
    {{ 'something' | uppercase}}
    {{ 'Descriptions bla bla' | limitTo: 8 }}
    ng-repeat="products in store.products | orderBy:'-price'">

# angular_store
