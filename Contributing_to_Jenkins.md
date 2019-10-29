# Contributing to Jenkins

Jenkins là một công cụ mã nguồn mở nên chúng ta có thể thực hiện contribute cho jenkins

### Bắt đầu

1. Chúng ta fork repo của jenkins trên github
2. Clone về máy tính cá nhân từ repo đã được fork
3. Cài đặt các công cụ thực hiện cho việc dev bao gồm:
   - JDK (Java Development Kit) 8 hoặc 11
   - Maven (Bắt buộc phải sử dụng từ phiên bản 3.5.4 trở lên)
   - Một số công cụ IDE có hỗ trợ việc import maven projects như ItelliJ, Netbeans, Eclipse
4. Thiết lập môi trường dev

Về việc contribute, chúng ta có thể bắt đầu bằng việc fix một số các issues, hoặc ở trong jenkins issue tracker (issues.jenkins-ci.org), chúng ta có thể đóng góp bằng cách tạo các issues ở trên trang issues.jenkins-ci.org hoặc đóng góp cách sửa lỗi lên 

### Về việc thực hiện building và debugging

Chúng ta có thể cài đặt jenkins bằng cách build jenkins core bằng maven

Cách đơn giản nhất để có được file jenkins.war (một định dạng tệp tin nén chứa các ứng dụng mạng chạy trên nền tảng java) chúng ta có thể chạy câu lệnh sau:

```bash
mvn clean package -pl war -am -DskipTests -Dspotbugs.skip
```

sau khi thực hiện câu lệnh này, file jenkins.war sẽ được tạo ở trong thư mục /war/target/jenkins.war trong thư mục mà chúng ta đã clone về. Sau đó chúng ta có thể sử dụng Java CLI để chạy Jenkins bằng cách:

```bash
java -jar jenkins.war
```

### ## Continous