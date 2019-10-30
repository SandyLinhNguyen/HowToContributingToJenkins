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

Jenkins core bao gồm unit và các function test, có ba loại test:

* light-test: chỉ có unit tests, không có function tests
* smoke-test: chạy các unit tests và một vài function tests
* all-tests: chạy tất cả các tests (đây là mặc định)

### Về việc thực hiện pull request

Các kho dự án mã nguồn mở của jenkins được lưu trữ tại github. Tất cả các thay đổi được submitted và code sẽ được review bằng quy trình pull request

Để submit một pull request:

1. Commit các thay đổi và push chúng về repo mà bạn đã fork về trên github

2. New pull request

3. Chọn jenkinsci as base fork and master as base, sau đó click create pull request

   Đội ngũ quản lý sẽ xem xét để đưa vào nhanh chính hoặc đưa vào LTS tùy trường hợp

4. Điền các thông tin vào các trường description rồi click pull request

5. Cuối cùng là đợi CI results/reviews

Note:

Nếu không nhận được feedback sau 3 ngày thì có thể ping tới @jenkinsci/code-reviewers thông qua CC

Thường thì họ sẽ merge request sau hai phiếu vote từ viewer hoặc 1 vote và 1 tháng delay mà không có thêm vote nào

### Quá trình thực hiện contribute

###### Meet

* Gặp gỡ, chia sẻ kinh nghiệm của mình với những người dùng jenkins khác có thể bằng cách là tổ chức hoặc tham gia các buổi meet up

* Tham gia các sự khác với sự hiện diện của Jenkins

###### Help

* Nếu là một người dùng có kinh nghiệm, có thể giúp người khác tận dụng tối đa jenkins, như là thông qua mail, các group channel, Reddit, stackoverflow

###### Cung cấp các phản hồi

* Tạo các báo cáo về issue

* Thực hiện các đánh giá, feedback

###### Contributor

* Đóng góp mã, tài liệu, bản dịch  giúp cải thiện Jenkins và plugin

###### Write code

* Có thể tham gia đóng góp viết plugin và các thành phần liên quan

###### Translate

* Có thể tham gia dịch ngôn ngữ từ tiếng anh sang các ngôn ngữ địa phương

###### Document

* Cải thiện các tài liệu của jenkins và các plugins để giúp những người khác bắt đầu dễ dàng hơn và nhanh hơn

