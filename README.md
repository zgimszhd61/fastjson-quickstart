# fastjson-quickstart

`fastjson` 是一个常用的 Java 库，用于将 Java 对象转换成 JSON 格式的字符串，以及将 JSON 字符串解析成 Java 对象。这个库因其高性能和简便的 API 而受到许多开发者的青睐。下面列举了一些 `fastjson` 中的常用 API：

1. **对象序列化** - 将 Java 对象转换为 JSON 字符串：
   - `JSON.toJSONString(Object object)`：将 Java 对象转换为 JSON 字符串。
   - `JSON.toJSONString(Object object, boolean prettyFormat)`：将 Java 对象转换成 JSON 字符串，可以选择是否美化输出（格式化）。

2. **对象反序列化** - 将 JSON 字符串解析为 Java 对象：
   - `JSON.parseObject(String text, Class<T> clazz)`：将 JSON 字符串解析为 Java 对象。`clazz` 参数指定要解析成的目标对象类型。
   - `JSON.parseArray(String text, Class<T> clazz)`：将 JSON 字符串解析为特定类型的对象列表（数组）。

3. **泛型支持** - 支持泛型的 JSON 解析：
   - `TypeReference`：用于处理泛型，因为 Java 泛型在运行时会被擦除。通过创建一个匿名内部类，可以指定具体的泛型类型。

   示例代码：
   ```java
   List<MyClass> myList = JSON.parseObject(jsonString, new TypeReference<List<MyClass>>(){});
   ```

4. **特性控制** - 控制序列化和反序列化的行为：
   - `SerializerFeature`：枚举类型，定义了序列化过程中可用的各种特性，如 `QuoteFieldNames`, `UseISO8601DateFormat` 等。
   - `Feature`：枚举类型，定义了解析过程中的控制特性，如 `IgnoreNotMatch` 等。

5. **直接解析 JSON 对象和数组**：
   - `JSON.parse(String text)`：直接解析 JSON 字符串到 `JSONObject` 或 `JSONArray`，依据实际内容自动判断。
   - `JSONObject` 和 `JSONArray`：可以直接操作 JSON 对象和数组，类似于其他语言中的字典和列表。

`fastjson` 的使用非常灵活，这些 API 覆盖了大部分常见的需求，从基本的序列化和反序列化到复杂的类型处理和特性控制。如果您有特定的应用场景，可能还需要查阅更详细的文档来了解如何使用 `fastjson` 的高级特性。
