# Network Util
A very small Java library for myself, that makes requesting sites very slightly easier.
Saves me pasting this function into like 50% of my projects.

### Usage
Thanks to [JitPak](https://jitpack.io/#scales-dev/Spreadsheet-Scripting)!
Replace TAG with a commit version or -SNAPSHOT to be on the bleeding edge

#### Gradle
```groovy
dependencies {
    implementation 'com.github.scales-dev:Network-Util:Tag'
    
    // https://github.com/google/gson
    implementation 'com.google.code.gson:gson:2.15.0'
}
```

#### Maven
```xml
<dependency>
    <groupId>com.github.scales-dev</groupId>
    <artifactId>Network-Util</artifactId>
    <version>Tag</version>
</dependency>
<dependency>
    <groupId>com.google.code.gson</groupId>
    <artifactId>gson</artifactId>
    <version>2.15.0</version>
</dependency>
```

### Example
```java
private static final String API_URL = "api";
public static final Map<String, String> HEADERS = Map.of(
        "Content-Type", "application/json",
        "Referer", "https://myexoticfruit.com/",
        "Origin", "https://myexoticfruit.com",
        "Accept", "application/json, text/plain, */*",
        "User-Agent", "Mozilla/5.0"
);

private static final Map<String, String> ITEM_DEFAULT_PARAMS = Map.of(
        "stuffAfterQuestionMark", "idk"
);


public static JsonObject getData() {
  return NetworkUtil.requestURL(API, Map.of(), HEADERS)
          .getAsJsonObject("data");
}
```