# 1. 使用策略模式，在if-else或者switch-case情况比较多的时候
```
 let strategy = {
            "S": function ( salary ){
                return salary*4;
            },
            "A": function ( salary ) {
                return salary*3;
            },
            "B": function ( salary ) { 
                return salary*2;
            }
        }
        let calculateBonus = function ( level, salary ) {
            return strategy[ level ]( salary );
        }
        console.log(calculateBonus('A', 20000)) 
```
