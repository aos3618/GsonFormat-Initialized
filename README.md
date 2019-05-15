# GsonFormat-Initialized

在原有GsonFormat基础上修改了：带有初始化值的 GsonFormat。
可以规避一些空指针异常

### 使用Code中的 .zip Install Plugin from disk 替换原有的 GsonFormat
### 效果如下：

```java
public class TestModel {

    /**
     * name : 小强
     * age : 16
     * msg : ["a","b"]
     * regex : ^http://.*
     */

    private String name;
    private int age;
    private String regex;
    private List<String> msg;

    public String getName() {
        return name == null ? "" : name;   //生成有空判断的 get方法
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public String getRegex() {
        return regex == null ? "" : regex;
    }

    public void setRegex(String regex) {
        this.regex = regex;
    }

    public List<String> getMsg() {
        if (msg == null) {
            msg = new ArrayList<>();    //默认初始化的 List 或 Map
        }
        return msg;
    }

    public void setMsg(List<String> msg) {
        this.msg = msg;
    }
}
```
