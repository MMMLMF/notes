## 1 springboot @Valid注解对输入的参数进行校验

限制 说明 
@Null 限制只能为null

@NotNull 限制必须不为null 

@AssertFalse 限制必须为false 

@AssertTrue 限制必须为true 

@DecimalMax(value) 限制必须为一个不大于指定值的数字 

@DecimalMin(value) 限制必须为一个不小于指定值的数字 

@Digits(integer,fraction) 限制必须为一个小数，且整数部分的位数不能超过integer，小数部分的位数不能超过fraction 

@Future 限制必须是一个将来的日期 

@Max(value) 限制必须为一个不大于指定值的数字 

@Min(value) 限制必须为一个不小于指定值的数字 

@Pattern(value) 限制必须符合指定的正则表达式 

@Size(max,min) 限制字符长度必须在min到max之间 

@Past 验证注解的元素值（日期类型）比当前时间早 

@NotEmpty 验证注解的元素值不为null且不为空（字符串长度不为0、集合大小不为0）

@NotBlank 验证注解的元素值不为空（不为null、去除首位空格后长度为0），不同于@NotEmpty，@NotBlank只应用于字符串且在比较时会去除字符串的空格 

@Email 验证注解的元素值是Email，也可以通过正则表达式和flag指定自定义的email格式 

## 2 对项目中的error的返回数据做统一处理

```java
@RestController
@RequestMapping("${server.error.path:${error.path:/error}}")
public class QaErrorController implements ErrorController {
    @Override
    public String getErrorPath() {
        return "/error";
    }

    @RequestMapping
    public ResultBean doHandleError() {
        return new ResultBean(ResultCode.TIMEOUT);
    }
}
```

## 3 对项目中的exception做统一处理

```java

@ControllerAdvice
@ResponseBody
public class ExceptionHandlerAdvice {

    @ExceptionHandler(Exception.class)
    public ResultBean handleException(Exception e) {
        e.printStackTrace();
        return new ResultBean(ResultCode.OTHER_ERROR);
    }

    @ExceptionHandler(HttpMessageNotReadableException.class)
    public ResultBean handleHttpMessageNotReadableException(HttpMessageNotReadableException e) {
        return new ResultBean(ResultCode.ILLEGAL_JSON);
    }

    @ExceptionHandler(NoNodeAvailableException.class)
    public ResultBean handleNoNodeAvailableException(NoNodeAvailableException e) {
        return new ResultBean(ResultCode.ES_TIMEOUT);
    }
}

```

