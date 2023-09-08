# Intro
Storybook là một công cụ thiết kế và phát triển những UI Components cho ứng dụng của bạn trên một môi trường hoàn toàn biệt lập. Storybook mang lại trải nghiện mới khi thiết kế những UI components tưởng chừng chỉ dừng lại ở khâu design trước khi chuyển sang giai đoạn code Frontend.
# Concept of Storybook

Hãy lấy ví dụ trực quan, hãy tưởng tượng bạn đối mặt với một trong hai trường hợp sau trong dự án Frontend:

- Trường hợp lý tưởng: Design đã xong 98%, đã có StyleGuide, gần như các phần core là cố định sẽ không có thay đổi lớn nào.
- Trường hợp éo le: Design mới chỉ hoàn thành 60%, dự án lên kế hoạch làm những phần chính Frontend song song với design, vừa làm vừa cập nhật.
Trong cả hai trường hợp trên, mặc dù có được đưa vào bất cứ hoàn cảnh nào, chúng ta cũng sẽ chọn một cách làm 'chưa đúng', tôi sẽ nói rõ điều 'chưa đúng' này ở dưới đây:

Trường hợp éo le, bạn hoàn toàn có lý do để chia nhau ra code những page đã hoàn thành trước, làm được gì hay được đó, đơn giản vì chưa có StyleGuide cover toàn bộ dự án. Nhưng thực tế là dù có được đưa vào trường hợp lý tưởng, chúng ta cũng bỏ qua bước thiết kế từng Component mà thường bắt tay ngay vào từng page cụ thể, và chỉ xem StyleGuide như một tài liệu tham khảo, người trước làm chưa đủ thì người sau xem lại và bổ sung.

Cách này có nhiều rủi ro nhưng lại được áp dụng, lời lý giải có thể chấp nhận được:
- Các task hoàn thành page cụ thể mang lại 'cảm giác' value lớn hơn và dự án đang đi nhanh hơn.
- Thiết kế từng UI Component xong show ra như thế nào cho ổn? Rất khó có thể có một Template sẵn để áp dụng. Tạo riêng một route trong dự án để show UI Components?
- Ai làm phần này? Một người làm thì quá nặng, chia ra cả team làm thì quá rối.

# Storybook sẽ là một lời giải cho bài toán này...

Chúng ta sẽ gọi các UI Components vừa thực hiện ra và gán cho nó một 'câu chuyện' - Đó chính là hiển thị toàn bộ các props và state. Bất cứ ai khi viết xong Components của mình đều có thể tạo ra câu chuyện của mình được, hoàn toàn không conflict.

Những câu chuyện này hiển thị đầy đủ và độc lập - Storybook chạy ở một port riêng, có thể chạy song song với dự án. Việc này giúp ích chúng ta rất nhiều khi chỉnh sửa và theo dõi trạng thái của các elements, rất trực quan và nhanh chóng.
![image](https://storybook.js.org/tutorials/intro-to-storybook/react-native-task-component-completed.gif)




https://storybook.js.org/tutorials/intro-to-storybook/react-native/en/simple-component/
https://viblo.asia/p/phat-trien-ui-cho-du-an-frontend-voi-storybook-eW65GEWLZDO
