# Làm thế nào để báo cáo một issues

Trong quá trình sử dụng jenkins, đôi khi chúng ta gặp một số các trường hợp có thể coi là lỗi, những lúc như vậy, chúng ta có thể vào một trang tìm kiếm là [https://issues.jenkins-ci.org/](https://issues.jenkins-ci.org/) để tiến hành tìm kiếm các cách sửa lỗi, nhưng có những trường hợp các lỗi đó có thể chưa từng có ai gặp phải hoặc chưa có ai đăng lỗi đó lên, chúng ta có thể tạo một báo cáo về lỗi đó lên [https://issues.jenkins-ci.org/](https://issues.jenkins-ci.org/) (Hay còn được gọi là Jenkins Jira).

Note: Jenkins Jira không phải là một trang phục vụ hỗ trợ, nếu chúng ta cần sự hỗ trợ hoặc có một vài câu hỏi thì chúng ta có thể thông qua chat hoặc email trực tiếp:

* Chat: Đăng ký tài khoản freenode và join vào channel là [https://webchat.freenode.net/#jenkins](https://webchat.freenode.net/#jenkins) để đặt các câu hỏi, nhưng thường phản hồi thường chậm.

  Hoặc có thể thông qua tham gia các buổi meeting, các sự kiện của cộng đồng jenkins...

* Mailing: Có thể gửi mail thông qua các mail sau:

  * [jenkinsci-users@googlegroups.com](jenkinsci-users@googlegroups.com)

  * [jenkinsci-dev@googlegroups.com](mailto:jenkinsci-dev@googlegroups.com)

  * [events@lists.jenkins-ci.org](mailto:events@lists.jenkins-ci.org)

  * [jenkinsci-jam@googlegroups.com](mailto:jenkinsci-jam@googlegroups.com)

  * [infra@lists.jenkins-ci.org](mailto:infra@lists.jenkins-ci.org)

  * [jenkinsci-docs@googlegroups.com](mailto:jenkinsci-docs@googlegroups.com)

    Ở trên là các trang hỗ trợ ngôn ngữ tiếng anh

### Trước khi tạo một issue

Đầu tiên, chúng ta cần định nghĩa thể loại issue đó, có ba loại issue chính:

* Bug: Có một thành phần nào đó không hoạt động
* New Feature: Muốn thêm chức năng mới
* Improvement: Thay đổi chức năng nào đó ở hiện tại

Ngoài ra còn có hai loại nữa là patch(bản vá) và task, nhưng không được sử dụng rộng rãi, và muốn tạo thì cần phải tạo một issue thuộc một trong ba loại trên và tạo pull request lên github

###### Trước khi báo cáo bug

* Kiểm tra bug mình muốn báo cáo đã có trước hay chưa
* Đảm bảo vấn đề là của jenkins
* Kiểm tra changelogs ([https://jenkins.io/changelog/](https://jenkins.io/changelog/)) để xem issue đã được giải quyết ở các version gần nhất chưa.

###### Trước khi yêu cầu Improvement hoặc Feature

* Kiểm tra các phiên bản mới của jenkins hoặc plugin đang đề cập đã được phát hành chưa, có thể đã có tính năng này
* Tìm kiếm JIRA, nếu có rồi chúng ta có thể bỏ phiếu để giúp xác định nhu cầu và độ ưu tiên cho các yêu cầu, nên cần tìm kỹ thay vì báo cáo trùng lặp

### Tạo một issue

Chúng ta cần tạo một tài khoản nếu chưa có, rồi tiến hành Create Issue trên trang chủ JIRA [https://issues.jenkins-ci.org/](https://issues.jenkins-ci.org/)

* Về Project chọn:
  * Jenkins: các vấn đề của jenkins
  * Security Issues: muốn báo cáo một security issue
  * Infrastructure : Một vài services chạy bởi jenkins project
* Summary: Điền một đoạn ngắn nhưng đủ nghĩa, giống như là một description
* Priority: Mức độ ưu tiên, Nên xem [https://issues.jenkins-ci.org/secure/ShowConstantsHelp.jspa?decorator=popup#PriorityLevels](https://issues.jenkins-ci.org/secure/ShowConstantsHelp.jspa?decorator=popup#PriorityLevels) để tính toán mức độ ưu tiên
* Component: Chọn thành phần liên quan, một issue thường liên quan tới chính jenkins hoặc plugin
* Asignee: Có thể để automatic cũng được, chọn ngẫu nhiên người xem xét issue đó thay vì chọn người trong list của họ

### Các thông tin cần cung cấp chi tiết

Môi trường: 

* OS: (version, 32/64 bit, ubuntu, centos8 ..), thông tin về jenkins server, jenkins slave
* JRE/JDK: version, parameters (OpenJDK, Oracle JRE, Java 8, Java 11 ...)
* Jenkins versions, plugin versions
* Jenkins là chạy độc lập trên một con máy hay chạy container
* Cách cài jenkins: deb/rpm, windows installer, hoặc là chạy node như thế nào (Via SSH, command ...)
* Trình duyệt sử dụng (version)

Description: (Miêu tả một cách toàn diện về issue)

* Vấn đề xảy ra có phải sau khi thực hiện upgrade jenkins hoặc plugin? Nếu là vấn đề này thì nêu rõ phiên bản trước là gì, phiên bản hiện tại là gì? Downgrade có thể giải quyết được vấn đề hay không?
* Bao gồm log output và các error messages cả từ UI lẫn cả các máy node nếu có
* Mô tả lại step-by-step lại quá trình xảy ra vấn đề, nên chuyển đổi cấu hình sử dụng từ ngôn ngữ địa phương sang tiếng anh (giao diện jenkins)
* Cung cấp các thông tin về trường hợp xảy ra sự cố
* Nếu xảy ra khi tương tác với các hệ thống khác (VD: SCM), hãy mô tả về phiên bản cũng như các cấu hình liên quan

### Sau khi tạo xong issue

Đảm bảo là có phản hồi trả lời những yêu cầu được đưa ra để kịp thời giải quyết

Giữ issue updated:

* Nếu tìm thấy thông tin liên quan cần bổ sung, hãy thêm vào mô tả vấn đề hoặc viết vào bình luận
* Nếu các phiên bản mới của jenkins không bị ảnh hưởng bởi sự cố hoặc đã triển khai tính năng mình yêu cầu thì đảm bảo rằng sự cố đã được sửa.

