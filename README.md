# utl-q-modifier-in-macro-and-datastep-scan-function-i-did-not-know-that
Q modifier in macro and datastep scan function i did not know that
    Q modifier in macro and datastep scan function i did not know that                                                                   
                                                                                                                                         
      Problem parse                                                                                                                      
          "1. TILE 28 días (%)"n    "2. TILE 91 días (%)"n    "3. TILE 93 días (%)"n                                                     
                                                                                                                                         
      Into                                                                                                                               
           "1. TILE 28 días (%)"n                                                                                                        
           "2. TILE 91 días (%)"n                                                                                                        
           "3. TILE 93 días (%)"n                                                                                                        
                                                                                                                                         
      Two solutions                                                                                                                      
                                                                                                                                         
          a. macro q modifier                                                                                                            
             https://communities.sas.com/t5/user/viewprofilepage/user-id/159                                                             
                                                                                                                                         
          b. dosubl                                                                                                                      
             I prefer this because there is no need to learn the qwirks of the macro language.                                           
             Forces you to expand your knowledge of datastep functionality.                                                              
             Allows the use of a do loop. Macro do is not supported in open code.                                                        
             MOves the macro text into the datastep where future changes are easier?                                                     
                                                                                                                                         
    github                                                                                                                               
    https://tinyurl.com/y7hxh77p                                                                                                         
    https://github.com/rogerjdeangelis/utl-q-modifier-in-macro-and-datastep-scan-function-i-did-not-know-that                            
                                                                                                                                         
    https://tinyurl.com/y7hxh77p                                                                                                         
    https://communities.sas.com/t5/SAS-Programming/Scan-macro-variable-list-with-names-like-quot-this-is-the-first/m-p/668932            
                                                                                                                                         
    You need this macro                                                                                                                  
                                                                                                                                         
    %macro dosubl(arg);                                                                                                                  
      %let rc=%qsysfunc(dosubl(&arg));                                                                                                   
    %mend dosubl;                                                                                                                        
                                                                                                                                         
    /*                   _                                                                                                               
    (_)_ __  _ __  _   _| |_                                                                                                             
    | | `_ \| `_ \| | | | __|                                                                                                            
    | | | | | |_) | |_| | |_                                                                                                             
    |_|_| |_| .__/ \__,_|\__|                                                                                                            
            |_|                                                                                                                          
    */                                                                                                                                   
                                                                                                                                         
    %let vars="1. TILE 28 días (%)"n "2. TILE 91 días (%)"n "3. TILE 93 días (%)"n;                                                      
                                                                                                                                         
    /*           _               _                                                                                                       
      ___  _   _| |_ _ __  _   _| |_                                                                                                     
     / _ \| | | | __| `_ \| | | | __|                                                                                                    
    | (_) | |_| | |_| |_) | |_| | |_                                                                                                     
     \___/ \__,_|\__| .__/ \__,_|\__|                                                                                                    
                    |_|                                                                                                                  
    */                                                                                                                                   
                                                                                                                                         
    Create three macro variables v1, v2 and v3;                                                                                          
                                                                                                                                         
       v1= "1. TILE 28 días (%)"n                                                                                                        
       v2= "2. TILE 91 días (%)"n                                                                                                        
       v3= "3. TILE 93 días (%)"n                                                                                                        
                                                                                                                                         
    %put &=v1;                                                                                                                           
                                                                                                                                         
    /*         _       _   _                                                                                                             
     ___  ___ | |_   _| |_(_) ___  _ __  ___                                                                                             
    / __|/ _ \| | | | | __| |/ _ \| `_ \/ __|                                                                                            
    \__ \ (_) | | |_| | |_| | (_) | | | \__ \                                                                                            
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|___/                                                                                            
     _ __ ___   __ _  ___ _ __ ___     __ _                                                                                              
    | `_ ` _ \ / _` |/ __| `__/ _ \   / _` |                                                                                             
    | | | | | | (_| | (__| | | (_) | | (_| |                                                                                             
    |_| |_| |_|\__,_|\___|_|  \___/   \__, |                                                                                             
                                         |_|                                                                                             
    */                                                                                                                                   
                                                                                                                                         
                                                                                                                                         
    %let vars="1. TILE 28 días (%)"n "2. TILE 91 días (%)"n "3. TILE 93 días (%)"n;                                                      
                                                                                                                                         
                                                                                                                                         
    %symdel v1 v2 v3 / nowarn;                                                                                                           
                                                                                                                                         
    %let v1 = %scan(&vars,1,%str( ),q);                                                                                                  
    %let v2 = %scan(&vars,2,%str( ),q);                                                                                                  
    %let v3 = %scan(&vars,3,%str( ),q);                                                                                                  
                                                                                                                                         
    %put &=v1;                                                                                                                           
    %put &=v2;                                                                                                                           
    %put &=v3;                                                                                                                           
                                                                                                                                         
    v1= "1. TILE 28 días (%)"n                                                                                                           
    v2= "2. TILE 91 días (%)"n                                                                                                           
    v3= "3. TILE 93 días (%)"n                                                                                                           
                                                                                                                                         
    /*   _                 _     _                                                                                                       
      __| | ___  ___ _   _| |__ | |                                                                                                      
     / _` |/ _ \/ __| | | | `_ \| |                                                                                                      
    | (_| | (_) \__ \ |_| | |_) | |                                                                                                      
     \__,_|\___/|___/\__,_|_.__/|_|                                                                                                      
                                                                                                                                         
    */                                                                                                                                   
                                                                                                                                         
    %let vars="1. TILE 28 días (%)"n "2. TILE 91 días (%)"n "3. TILE 93 días (%)"n;                                                      
                                                                                                                                         
    %symdel v1 v2 v3 / nowarn;                                                                                                           
                                                                                                                                         
    %dosubl('data _null_;                                                                                                                
               do i=1 to 3;                                                                                                              
                  v=scan(symget("vars"),i," ","Q");call symputx(cats("v",i),v);                                                          
               end;                                                                                                                      
             run;quit;');                                                                                                                
                                                                                                                                         
    %utlnopts;                                                                                                                           
                                                                                                                                         
    %put &=v1;                                                                                                                           
    %put &=v2;                                                                                                                           
    %put &=v3;                                                                                                                           
                                                                                                                                         
    v1= "1. TILE 28 días (%)"n                                                                                                           
    v2= "2. TILE 91 días (%)"n                                                                                                           
    v3= "3. TILE 93 días (%)"n                                                                                                           
                                                                                                                                         
                                                                                                                                         
