---
marp: true
theme: gaia
class: lead
---

<style scoped>
section {
  display: flex;
  justify-content: center;
  align-items: center;
}
h1 {
  text-align: center;
  margin: 0;
  font-size: 2.5em;
  border-bottom: none;
}
</style>

# MITRE ATT&CK Foundation checkpoint

---
<!-- class: default -->

<style scoped>
h1 {
  text-align: center;
  margin-top: 0px;
  padding-bottom: 10px;
  border-bottom: none;
}
h4 {
  border-bottom: none;
  margin-top: 10px;
  font-size: 30px;
}
p, li {
  font-size: 26px;
  line-height: 1.6;
  margin-bottom: 20px;
}
strong {
  color: #0056b3;
}
</style>

# Kiến thức cơ bản về MITRE ATT&CK

#### ATT&CK framework

* **Motivation:** Được tạo ra để hỗ trợ threat-informed defense và tập trung vào phần đỉnh của Pyramid of Pain (TTPs) thay vì các indicators cơ bản.
* **Purpose:** Được phát triển để ghi nhận, phân tích và ứng phó với các adversary behaviors trong thực tế dựa trên public report.
* **Matrices & Platforms:** Sử dụng các view dạng matrix để trực quan hóa mối quan hệ trong các domain công nghệ cụ thể, bao gồm Enterprise (Windows, macOS, Linux, Cloud), Mobile và ICS.

---
<!-- class: default -->

<style scoped>
h1 {
  text-align: center;
  margin-top: 0px;
  padding-bottom: 54px;
  border-bottom: none;
}
h4 {
  border-bottom: none;
  margin-top: 10px;
  font-size: 30px;
  padding-bottom: 20px;
}
p, li {
  font-size: 26px;
  line-height: 1.6;
  margin-bottom: 20px;
}
strong {
  color: #0056b3;
}
</style>

# Kiến thức cơ bản về MITRE ATT&CK

#### ATT&CK Architecture

* **Tactics (Why), Techniques and Sub-techniques (How):** Phân loại các mục tiêu của adversary và các phương thức cụ thể được sử dụng để đạt được chúng.
* **Procedures:** Cách thức triển khai chính xác một technique của adversary.
* **Tracking Threats:** Liên kết các behaviors với các Threat Groups, Campaigns và Software (Malware/Tools) cụ thể.


---
<!-- class: default -->

<style scoped>
h1 {
  text-align: center;
  margin-top: 0px;
  padding-bottom: 54px;
  border-bottom: none;
}
h4 {
  border-bottom: none;
  margin-top: 10px;
  font-size: 30px;
}
p, li {
  font-size: 26px;
  line-height: 1.6;
  margin-bottom: 20px;
}
strong {
  color: #0056b3;
}
</style>

# Kiến thức cơ bản về MITRE ATT&CK

#### Defensive countermeasures

* **Mitigations:** Các cấu hình và công cụ được thiết kế để ngăn chặn việc thực thi thành công các techniques.
* **Data Sources & Components:** Xác định các telemetry, sensors và logs cụ thể cần thiết để quan sát các behaviors.
* **Detections:** Các chiến lược phân tích được áp dụng trên dữ liệu thu thập được để nhận diện các techniques.

---
<!-- class: default -->

<style scoped>
h1 {
  text-align: center;
  margin-top: 0px;
  padding-bottom: 54px;
  border-bottom: none;
}
h4 {
  border-bottom: none;
  margin-top: 10px;
  font-size: 30px;
}
p, li {
  font-size: 26px;
  line-height: 1.6;
  margin-bottom: 20px;
}
strong {
  color: #0056b3;
}
</style>

# Kiến thức cơ bản về MITRE ATT&CK

#### Using ATT&CK

* **Common Language:** Thu hẹp khoảng cách giao tiếp giữa CTI, Red Teams và SOC Analysts để ngăn chặn các thiếu sót trong quá trình vận hành.
* **Adversary Emulation:** Mô phỏng known threats để thiết lập ưu tiên và đánh giá defensive gaps.
* **ATT&CK Navigator:** Được sử dụng để chú thích, chấm điểm và trực quan hóa khả năng bao quát của hệ thống phòng thủ

---
<!-- class: default -->

<style scoped>
h1 {
  text-align: center;
  margin-top: 0px;
  padding-bottom: 10px;
  border-bottom: none;
}
h4 {
  border-bottom: none;
  margin-top: 10px;
  font-size: 30px;
}
p, li {
  font-size: 26px;
  line-height: 1.6;
  margin-bottom: 20px;
}
strong {
  color: #0056b3;
}
</style>

# T1047 - WMI

#### Introduction

* **What is WMI:** Một công cụ quản trị cốt lõi của Microsoft được tích hợp sẵn trong Windows, cung cấp một interface để thực hiện local/remote system querying, configuration management và monitoring.
* **The LotL Advantage:** Bởi vì đây là một tiện ích thiết yếu, có sẵn và không thể gỡ nó mà không làm hỏng OS, các attackers thường lạm dụng nó cho các hoạt động Living-off-the-Land (LotL) nhằm bypass các signature-based security controls.
* **ATT&CK Mapping (T1047):** Framework này chính thức phân loại hành vi này thuộc Execution tactics.

