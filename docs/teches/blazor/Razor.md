# Razor

## 语法与表达式

Razor 的默认语言为HTML，但同时支持 C#，并使用 `@` 符号从 HTML 转换为 C#.

计算表达式：@后跟C#表达式，程序会计算表达式结果，并将结果渲染到HTML上。<mark style="background: #FFF3A3A6;">Razor保留关键字</mark> 除外。

保留关键字：Razor保留使用的关键字，如果@后的表达式为关键字那么它们不会被计算。

转义字符：@符号是一种转义字符，如果想要原样输出它，请使用两个@，即 `@@` 

隐式表达式：@后直接加C#代码的形式是隐式表达式，隐式表达式不能包含空格（await 除外）和尖括号。
>尖括号会被识别为HTML标记，导致编译错误。

显式表达式：@后加圆括号，圆括号内写C#代码的形式为显式表达式，即 `@()` ，显示表达式会计算圆括号里的所有内容。

## 代码块与控制结构

代码块：@后加大括号 `{}` 构成代码块结构，即 `@{}` ，代码块内的语言默认为C#，但标签会被转换为HTML。代码块中可以编写更多C#代码以及HTML，并且可以在HTML中使用@表达式。
>代码块内可以混合编写C#代码和HTML，HTML会被呈现页面，@表达式会被计算结果，纯C#代码不会被呈现。

示例：
```razor
@{
    void RenderName(string name)
    {
        <p>Name: <strong>@name</strong></p>
    }
    RenderName("Mahatma Gandhi");
    RenderName("Martin Luther King, Jr.");
}
```


控制结构：控制结构是对代码块的扩展，对于控制结构可以在代码块中使用C#常规语法，也可以直接使用控制结构语法。
- 条件语句：@if、@if-else if、@if-else if-else、@switch
```razor
@if (condition)
{

}
else if
{

}
else
{

}

@switch (value)
{
	case v1:
		break;
	case v2:
		break;
	default:
		break;
}
```
- 循环语句：@for、@foreach、@while、@dowhile
```razor
@for()
{

}

@foreach()
{

}

@while()
{

}

@do
{

}while();
```
- 复合语句：@using
```razor
@using()
{

}
```
- 异常处理：@try-catch-finally
```razor
@try
{

}
catch(Exception)
{

}
finally
{

}
```
- 锁：@lock
```razor
@lock()
{

}
```
- 注释：`@**@` 
```razor
@*
	注释
*@
```

## 指令

指令：在隐式表达式用不能使用保留关键字，因为 `@保留关键字` 构成了指令。指令通常用于更改视图分析方式或启用不同的功能。


| 指令 | 说明 | 示例 | 备注 |
|:---- |:---- |:---- |:---- |
| @     |      |      |      |
|      |      |      |      |
|      |      |      |      |
|      |      |      |      |