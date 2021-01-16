# 语言基础

## 关键字与保留字

| 字段   | 字段     | 字段     | 字段  | 字段    | 字段   | 字段       | 字段     |
| ------ | -------- | -------- | ----- | ------- | ------ | ---------- | -------- |
| break  | do       | in       | typof | case    | else   | instanceof | var      |
| new    | void     | while    | const | finally | super  | with       | continue |
| yield  | debugger | function | this  | default | if     | throw      | delete   |
| export | switch   | try      | catch | for     | import | ` `        | ` `      |

## 数据类型
 
 - Undefined:`undefined`
 - Null:`null`
 - Boolean:`true|false`
 - Number: IEEE754格式表示的整数和浮点数(范围:`Number.MIN_VALUE~Number.MAX_VALUE`)
 - String
 - Symbol
 - Object

### Undefined
 如果一个变量声明了未初始化,值是undefined,如果一个变量没有声明,值也是undefined,建议在声明变量时初始化默认值
### Null
  `typeof null` 返回 `object`

  undefined值是由null值派生而来,`null == undefined //true`

  如果使用一个变量保存对象,首选默认值null
### Boolean
  布尔值区分大小写,其他数据类型可以转成布尔值:

| 数据类型  | 可以转为true的值     | 可以转为false的值 |
| --------- | -------------------- | ----------------- |
| Boolean   | true                 | false             |
| String    | 非空字符串           | ""(空字符串)      |
| Number    | 非零数值(包括无穷值) | 0、NaN            |
| Object    | 任意对象             | null              |
| Undefined | 无                   | undefined         |
### Number
  `+0 === -0 //true`

  NaN,用来表示本来要返回数值的操作失败了(不是抛出错误),在其他语言中,用0除任意数值通常都会导致错误,但在ECMAScript中是返回NaN

  NaN不等于包括他自己的任何值,`NaN === NaN //false`

 - #### `isNaN()`
  用来判断一个值是否 **不是数值**
     - `isNaN(1)//false`
     - `isNaN('moxue')//true`
 - #### `Number()`
  转型函数用来将一个值转为数值,规则如下:
     - 布尔值
       - true ==> 1
       - false ==> 0
     - 数值直接返回
     - null ==> 0
     - undefined ==> NaN
     - 字符串
       - 如果字符串包含数值字符，包括数值字符前面带加、减号的情况，则转换为一个十进制数值。因此，Number("1")返回1，Number("123")返回123，Number("011")返回11（忽略前面的零）
       - 如果字符串包含有效的浮点值格式如"1.1"，则会转换为相应的浮点值（同样，忽略前面的零）
       - 如果字符串包含有效的十六进制格式如"0xf"，则会转换为与该十六进制值对应的十进制整数值
       - 如果是空字符串（不包含字符），则返回0
       - 如果字符串包含除上述情况之外的其他字符，则返回NaN
     - 对象，调用valueOf()方法，并按照上述规则转换返回的值。如果转换结果是NaN，则调用toString()方法，再按照转换字符串的规则转换
  
 - #### `parseInt()`
    - 如果第一个字符不是数值字符、加号或减号，parseInt()立即返回NaN
    - 如果第一个字符是数值字符、加号或减号，则继续依次检测每个字符，直到字符串末尾，或碰到非数值字符
 - #### `parseFloat()`
    > 与parseInt转换规则相同相同

### String
  ECMAScript中的字符串是不可变的,一经创建就不能在变,修改变量中的字符串值,会先销毁原来的字符串,然后将新的字符串赋值给这个变量

### Symbol
  Symbol实例是唯一、不可变的,用途是确保对象属性使用唯一标识符，不会发生属性冲突的危险,以下列出了一些方法和属性,要了解详细使用方法请查阅相关文档或者翻阅原书籍

  - #### `Symbol()`
  - #### `Symbol.for()`
  - #### `Object.getOwnProperty-Symbols()`
  - #### `Symbol.asyncIterator()`
  - #### `Symbol.hasInstance()`
  - #### `Symbol.isConcatSpreadable`
  - #### `Symbol.iterator()`
  - #### `Symbol.match()`
  - #### `Symbol.replace()`
  - #### `Symbol.search()`
  - #### `Symbol.species()`
  - #### `Symbol.split()`
  - #### `Symbol.toPrimitive()`
  - #### `Symbol.toStringTag`
  - #### `Symbol.unscopables`
  
### Object
每个Object的实例有以下属性和方法
- #### `constructor`
  > 用于创建当前对象的函数
- #### `hasOwnProperty(propertyName)`
  > 用于判断当前对象实例（不是原型）上是否存在给定的属性
- #### `isPrototypeOf(object)`
  > 用于判断当前对象是否为另一个对象的原型
- #### `propertyIsEnumerable(propertyName)`
  > 用于判断给定的属性是否可以使用for-in语句枚举
- #### `toLocaleString()`
  > 返回对象的字符串表示，该字符串反映对象所在的本地化执行环境
- #### `toString()`
  > 返回对象的字符串表示
- #### `valueOf()`
  > 返回对象对应的字符串、数值或布尔值表示

## with语句
 > with语句的用途是将代码作用域设置为特定的对象，其语法是：with (expression) statement;