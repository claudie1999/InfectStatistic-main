## **代码风格**

**缩进**

1. 所有代码缩进使用一个tab字符，但需注意不同环境下tab控制符的解释不同，统一设置为一个tab字符为4个空格符。

**变量命名**

1. 代码中命名不允许以下划线或美元符号开始，也不允许以下划线或美元符号结束。

2. 命名应以中文词汇相对应的英文方式命名，除非该词汇无准确的英文释义或者该词汇还未出现国际化的英文形式。否则不允许使用拼音与英文混合的方式命名。

3. 方法名、参数名、成员变量、局部变量统一使用驼峰命名。

   ```java
   getArgsMap/sortByName   //正例
   ```

4. 常量名全部大写，并采用完整单词，单词间用下划线隔开。不能省略关键词，易造成语义模糊。

   ```java
   SCHOOL_TOTAL_STUDENTS    //正例
   SCHOOL_TOTAL_FEMALE_TEACHER       //正例
   ```

5. 抽象类以Abstract或Base开头，异常类以Exception结尾，枚举类以Enum结尾。

6. 使用人们熟悉并且具有实际意义的词汇。

   

**每行最多字符数**

1. 每行代码不超过100个字符，“字符”表示任何Unicode代码点。除非另有说明，否则超出该限制的任何行都必须进行换行。

2. 每个Unicode代码点都算作一个字符，即使其显示宽度更大或更小。例如当使用全角字符，则可以选择在此规则严格要求的位置之前换行。

3. 例外情况：

   - 不能遵守列限制的行（例如长URL或长的JSNI方法参考）；
   - package和import语句；
   - 注释中的命令行，可以将其剪切并粘贴到外壳中。

**函数最大行数**

1. 函数最多不超过200行。

**函数、类命名**

1. 软件包名称均为小写字母，连续的单词简单的连接在一起（没有下划线），例如：

   ```
   com.example.deepspace   //正例
   com.example.deepSpace/com.example.deep_space   //反例
   ```

2. 类名用UpperCamelCase编写。类名通常是名词或者名词短语，例如Character或ImmutableList。

3. 接口名称也可以是名词或者名词短语，例如List，但有时也可以是形容词或形容词短语，例如Readable。

4. 测试类的名称以要测试的类的名称开头，以Test结尾，例如：HashTest。

5. 方法名用lowerCamelCase编写。方法名通常是动词或动词短语，例如：sendMessage或stop。

6. JUnit测试方法名称中，用下划线分隔名称的逻辑组成部分，每个组成部分均用lowerCamelCase编写，例如：<methodUnderTest>_<state>。

   

**常量**

1. 常量名称使用CONSTANT_CASE，所有字母大写，单词之间用下划线隔开。

**空行规则**

1. 类的连续成员函数和初始化函数之间：即字段、构造函数、方法、嵌套类、静态初始化方法和实例初始化方法之间需要空行。

**注释规则**

1. 注释独占一行，用于类，方法和构造函数中：

   ```java
   ＠Override
   @Nullable
   public String get() {
       ...
   }
   //只要是合法的，重写＠Override的注解能用则用
   
   //例外: 单个注解可和函数签名第一行出现在同一行中
   @Override public int hashCode() {
       ...
   }
   
   //用于字段的注解随文档块出现，也可允许出现在同一行
   @XXX @YYY DataLoader loader;
   ```

2. **注释风格统一使用**Javadoc方式：

   ```java
   /**
    * 用于描述方法或类
    */
    
   /** 单行形式，一般用于描述类的变量 */
   
   //　用于描述方法内部的单个语句
   ```

   Javadoc有一些约定俗称的标记，例如

   - 除首段落，每个段落第一个单词前都有标签``，并且它和第一个单词没有空格；
   - Javadoc标记按如下顺序出现: `@param`,`@return`,`@throws`,`@deprecated`，且描述都不能为空；
   - 一个单行的简要片段，应该写成`/** get xxx*/`,而不是`/** @return xxx*/`。

**操作符前后空格**

1. 任何保留字与紧随其后的左括号；如if,for,catch等。
2. 任何保留字与其前面的右大括号，如else。
3. 任何大左括号前。
4. 任何二元或三元运算符两侧都要使用空格，也适用于类运算符。
5. 在, : ; )后都要添加空格。

**异常处理**

1. .使用不受检查、运行时的异常来报告可能在程序逻辑中出错的严重未查明错误。

2. 使用检查异常来报告可能发生，而在正常的程序运行时极少发生的错误。

3. 用返回代码报告可预知的状态改变。

4. 仅转化异常来添加信息。

5. 不要私自处置运行时或者错误异常。

6. 用finally语句块释放资源。

7. 捕获的异常不能忽视，必须响应。如果catch块确实不需要回应，必须要加注释以说明；另外如果能确保测试的方法会抛出一个期望的异常，就没必要加注释：

   ```java
   try {
       xxx;
       fail();
   } catch (NoSuchElementException expected) {
   }
   ```

**其他规则**

1. 在非空块和块状结构时(如类，方法的主体，条件语句或循环语句)，要使用大括号，并且遵循K&R风格：

   ```java
   int hello() { //左大括号之前不换行，之后换行
   　　//函数体中若是语句等的终止，右大括号后换行，否则不换行
      if (xxx) {
         //do something
      }
      
      if (xxx) {
        //do something
      } else {
        //do other thing
      }
   }　//右大括号前换行
   ```
