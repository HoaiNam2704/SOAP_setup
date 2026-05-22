# Lưu ý về phiên bản Java

## Project hiện dùng JDK 17

Trong `pom.xml`:

```xml
<maven.compiler.release>17</maven.compiler.release>
```

và:

```xml
<release>17</release>
```

---

# Kiểm tra Java trước khi build

Kiểm tra Java:

```bash
java -version
```

Kiểm tra Maven:

```bash
mvn -version
```

---

# Nếu máy dùng JDK 21

Có thể đổi trong `pom.xml`:

```xml
<maven.compiler.release>21</maven.compiler.release>
```

và:

```xml
<release>21</release>
```

---

# Nếu bị lỗi Maven compile

Chạy:

```bash
mvn clean install -U
```

---

# Nếu Maven bị lỗi cache dependency

Xóa cache Maven:

Windows:

```text
C:\Users\YOUR_NAME\.m2\repository
```

Sau đó build lại:

```bash
mvn clean install
```

---

# Nếu đổi tên project

Ví dụ đổi sang:

```text
final_soap
```

thì sửa trong `pom.xml`:

```xml
<artifactId>final_soap</artifactId>
```

Có thể sửa thêm:

```xml
<groupId>com.finalsoap</groupId>
```

---

# Sau khi sửa pom.xml

Luôn chạy lại:

```bash
mvn clean install
```

để Maven generate lại source code từ WSDL.
