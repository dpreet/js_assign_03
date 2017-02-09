# Closure
                                                    
   SCOPE: Scope generally means range of view or space for activity.Whenever a function is declared, it creates its own scope which 
   means the variables declared within a particular function are accessible only in that function/wihtin scope or we can say that 
   they work in their own space of activity whereas global variables have a vast scope.
          
   SCOPE CHAIN: when we traverse within different scopes form a scope chain. Moving from local to gloabl or global to local scope
                forms into a scope chain.
                
    
              ------------------------------------------CLOSURES----------------------------------------------
             
              function basic(n) {
                              
                              var localVariable = n ;
                              return localVariable ;
                              
                                }
              console.log( basic(1));
               console.log(basic(2));
               
 In above example function basic returns the localVariable two times. When this functon is called second time, 
 first instance of this variable is overwritten and replaced by value 2. But what if in future we need the first value????
     
  CLOSURE: It is a kind of capturing function which separates an object from its original scope and add it to its own scope
           forever.
     
  what we are going to do is instead of returning the variable directly we will return a function and save that function in a 
  global variable that is out of functions' scope. Like this:
   
             function basic(n) {
                              
                       var localVariable = n ;
                       return function() { return localVariable ; } ;
                              
                                }
                                
              var globalVariable1 =  basic(1) ;          
              var globalVariable2 =  basic(2) ;  
              console.log( globalVariable1( ));
              console.log( globalVariable2( ));
              
 After changing few things in the previous example, now we are able to preserve two different instances of a variable. We enclosed 
 value 1 to be in the scope of function globalVariable1() and same with 2. Now no matter how many times the function is called
 and value of localVariable is changed , closure functions will always be able to refer a specific instance of a local variable.
 
 
 REFERENCES:
 
 https://community.risingstack.com/explaining-javascript-closure-scope-chain-examples/
 
 https://www.youtube.com/watch?v=yiEeiMN2Khs
 
 http://eloquentjavascript.net/03_functions.html
