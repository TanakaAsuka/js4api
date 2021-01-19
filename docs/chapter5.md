# 基本引用类型
本章包含大量API
## Date
> 引用值（或者对象）是某个特定引用类型的实例。在ECMAScript中，引用类型是把数据和功能组织到一起的结构。
> 
> Date类型将日期保存为自协调世界时（UTC，Universal  Time  Coordinated）时间1970年1月1日午夜（零时）至今所经过的毫秒数。

- #### `Date.parse()`
  > 将字符串转换为表示该日期的毫秒数
- #### `Date.UTC()`
  > 也返回日期的毫秒表示，但使用的是跟Date.parse()不同的信息来生成这个值，它创建的是本地日期，不是GMT日期
- #### `toLocaleString()`
  > 返回与浏览器运行的本地环境一致的日期和时间
- #### `toString()`
  > 返回带时区信息的日期和时间，时间以24小时制（0~23）表示
- #### `toDateString()`
  > 显示日期中的周几、月、日、年（格式特定于实现）
- #### `toTimeString()`
  > 显示日期中的时、分、秒和时区（格式特定于实现）
- #### `toLocaleDateString()`
  > 显示日期中的周几、月、日、年（格式特定于实现和地区）
- #### `toLocaleTimeString()`
  > 显示日期中的时、分、秒（格式特定于实现和地区）
- #### `toUTCString()`
  > 显示完整的UTC日期（格式特定于实现）
- #### `getTime()`
  > 返回日期的毫秒表示；与valueOf()相同
- #### `setTime(milliseconds)`
  > 设置日期的毫秒表示，从而修改整个日期
- #### `getFullYear()`
  > 返回4位数年
- #### `getUTCFullYear()`
  > 返回UTC日期的4位数年
- #### `setFullYear(year)`
  > 设置日期的年（year必须是4位数）
- #### `setUTCFullYear(year)`
  > 设置UTC日期的年（year必须是4位数）
- #### `getMonth()`
  > 返回日期的月（0表示1月，11表示12月）
- #### `getUTCMonth()`
  > 返回UTC日期的月（0表示1月，11表示12月）
- #### `setMonth(month)`
  > 设置日期的月（month为大于0的数值，大于11加年）
- #### `setUTCMonth(month)`
  > 设置UTC日期的月（month为大于0的数值，大于11加年
- #### `getDate()`
  > 返回日期中的日（1~31）
- #### `getUTCDate()`
  > 返回UTC日期中的日（1~31）
- #### `setDate(date)`
  > 设置日期中的日（如果date大于该月天数，则加月）
- #### `setUTCDate(date)`
  > 设置UTC日期中的日（如果date大于该月天数，则加月）
- #### `getDay()`
  > 返回日期中表示周几的数值（0表示周日，6表示周六）
- #### `getUTCDay()`
  > 返回UTC日期中表示周几的数值（0表示周日，6表示周六）
- ### `getHours()`
  > 返回日期中的时（0~23）
- #### `getUTCHours()`
  > 返回UTC日期中的时（0~23）
- #### `setHours(hours)`
  > 设置日期中的时（如果hours大于23，则加日）
- #### `setUTCHours(hours)`
  > 设置UTC日期中的时（如果hours大于23，则加日）
- #### `getMinutes()`
  > 返回日期中的分（0~59）
- #### `getUTCMinutes()`
  > 返回UTC日期中的分（0~59）
- #### `setMinutes(minutes)`
  > 设置日期中的分（如果minutes大于59，则加时）
- #### `setUTCMinutes(minutes)`
  > 设置UTC日期中的分（如果minutes大于59，则加时）
- #### `getSeconds()`
  > 返回日期中的秒（0~59）
- #### `getUTCSeconds()`
  > 返回UTC日期中的秒（0~59）
- #### `setSeconds(seconds)`
  > 设置日期中的秒（如果seconds大于59，则加分）
- #### `setUTCSeconds(seconds)`
  > 设置UTC日期中的秒（如果seconds大于59，则加分）
- #### `getMilliseconds()`
  > 返回日期中的毫秒
- #### `getUTCMilliseconds()`
  > 返回UTC日期中的毫秒
- #### `setMilliseconds(milliseconds)`
  > 设置日期中的毫秒
- #### `setUTCMilliseconds(milliseconds)()`
  > 设置UTC日期中的毫秒
- #### `getTimezoneOffset()`
  > 返回以分钟计的UTC与本地时区的偏移量（如美国EST即“东部标准时间”返回300，进入夏令时的地区可能有所差异）

## RegExp
匹配模式：
- g：全局模式，表示查找字符串的全部内容，而不是找到第一个匹配的内容就结束。
- i：不区分大小写，表示在查找匹配时忽略pattern和字符串的大小写。
- m：多行模式，表示查找到一行文本末尾时会继续查找。
- y：粘附模式，表示只查找从lastIndex开始及之后的字符串。
- u：Unicode模式，启用Unicode匹配。
- s：dotAll模式，表示元字符.匹配任何字符（包括\n或\r）。

元字符：
> ( [ { \ ^ $ | ) ] } ? * + .

### RegExp实例属性
每个RegExp实例都有下列属性，提供有关模式的各方面信息:
- global：布尔值，表示是否设置了g标记
- ignoreCase：布尔值，表示是否设置了i标记
- unicode：布尔值，表示是否设置了u标记
- sticky：布尔值，表示是否设置了y标记
- lastIndex：整数，表示在源字符串中下一次搜索的开始位置，始终从0开始
- multiline：布尔值，表示是否设置了m标记
- dotAll：布尔值，表示是否设置了s标记
- source：正则表达式的字面量字符串（不是传给构造函数的模式字符串），没有开头和结尾的斜杠
- flags：正则表达式的标记字符串。始终以字面量而非传入构造函数的字符串模式形式返回（没有前后斜杠）
  
### RegExp实例方法

- #### `exec()`
  > 这个方法只接收一个参数，即要应用模式的字符串。如果找到了匹配项，则返回包含第一个匹配信息的数组；如果没找到匹配项，则返回null。返回的数组虽然是Array的实例，但包含两个额外的属性：index和input。index是字符串中匹配模式的起始位置，input是要查找的字符串。这个数组的第一个元素是匹配整个模式的字符串，其他元素是与表达式中的捕获组匹配的字符串。如果模式中没有捕获组，则数组只包含一个元素
  >
  > 如果模式设置了全局标记，则每次调用exec()方法会返回一个匹配的信息。如果没有设置全局标记，则无论对同一个字符串调用多少次exec()，也只会返回第一个匹配的信息

- #### `test()`
  > 如果输入的文本与模式匹配，则参数返回true，否则返回false

## 原始值包装类型