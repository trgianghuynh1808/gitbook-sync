---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: false
---

# Clean code với FCIS pattern

> Khi làm việc với Vue3 mình thấy khá thoải mái và flexible với [Composition API](https://vuejs.org/api/composition-api-setup), tuy nhiên khi dự án càng lúc càng phức tạp cả về mặt technical và business dẫn tới việc logic xử lý của component hoặc page trở nên phức tạp.&#x20;
>
> Trong trường hợp này sẽ có nhiều cách để tối ưu code base như: cải thiện file structure, chia các component chi tiết hơn, tách các logic xử lý ra thành từng phần nhỏ...&#x20;
>
> Bài viết này mình sẽ giới thiệu một solution giúp mọi người có thể tách các logic xử lý Side effect, logic xử lý business ra thành từng phần nhỏ.  Giảm tính phức tạp, tăng khả năng maintenace cho dự án.&#x20;

### FCIS pattern là gì?

**FCIS** là viết tắt của Functional Core, Imperative Shell. Sinh ra nhằm mục đích khắc phục các vấn đề của Architecture truyền thống chủ yếu dựa theo mô hình Request-Response (có thể hiểu nôm na là mỗi Software Component đều sẽ có đầu vào là Request và đầu ra là Response)

Mindset chính của FCIS là tách **Business** và **Handle Side Effect** ra làm 2 phần chính:

#### 1. Functional Core (FC)

FC là phần core của hệ thống&#x20;
