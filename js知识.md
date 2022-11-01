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
# 4. ！！！！！
```
   info = {
        Username: "that.$store.state.user.userInfo.name",
        Appname: "main",
        Basetypeid: true,
        Modulename: "信号控制",
        Equipmentid: "101000033",
        Signalid: "130001180", // 1组
        Realvalue: "1",
      };

      for (let i in info) {
        // 如果用Basetypeid，那就传true
        //    let val;
        if (i == "Basetypeid") {
          let val = new wrappers.BoolValue().setValue(true);
          console.log(11111);
          console.log("-----", i, val);

          eval("signalWr.set" + i + "(val)");
        } else {
          let val = new wrappers.StringValue().setValue(info[i]);
          console.log(2222);
          console.log("-----", i, val);

          eval("signalWr.set" + i + "(val)");
        }
      }
      val 为啥会是undefined
```
