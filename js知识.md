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
# 2. 字面量
let test = 123  
=右边的值就是字面量，
`` `${}` `` 模板字符串，模板字面量
# 3. obj.name和obj[name]
中括号当中的属性名可以是数字，而点后面则不可以是数字  
但是key值写的时候是数字，最后都会转换为字符串  obj[123]，123是string，obj[123]效果上和obj['123']一样
# 4. && || 运算符(判断是否传入了数字)
&& 当数值参与逻辑与运算时，结果为true，那么会返回的会是第二个为真的值；如果结果为false，返回的会是第一个为假的值  
|| 当数值参与逻辑或运算时，结果为true，会返回第一个为真的值；如果结果为false，会返回第二个为假的值
```
let a=null; // undefined   8080 '8080'
let b=a && Number(a);
console.log(b,typeof b) 
```
