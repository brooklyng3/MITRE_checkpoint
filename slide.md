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

#### WMI & CIM Definitions

* **WMI:** Bản triển khai của Microsoft đối với Web-Based Enterprise Management (WBEM). Nó cung cấp một giao diện có sẵn cho việc local và remote system querying, configuration và monitoring.
* **CIM (Common Information Model):** Một tiêu chuẩn open-source định nghĩa một object-oriented schema không đặc trưng cho bất cứ nhà cung cấp nào để đại diện cho các hardware, software và network components.
* **The Relationship:** CIM thiết lập standard cho conceptual framework và baseline schema, trong khi WMI đóng vai trò là execution engine để triển khai standard này dành riêng cho Windows.

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

#### WMI Infrastructure & Components

* **WMI Service (winmgmt):** Core routing và processing broker chạy liên tục trong nền để bắt và chuyển các queries.
* **WMI Repository (OBJECTS.DATA):** Central binary database lưu trữ các định nghĩa, namespaces, và persistent object instances của CIM class tĩnh.
* **WMI Providers:** Các Component Object Model (COM) DLLs đảm nhiệm việc querying OS theo thời gian thực để populate data cho các namespaces như root\cimv2.

---
<!-- class: default -->

![bg fit](architecture.png)

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
table {
  margin-left: auto;
  margin-right: auto;
  margin-top: 30px;
  font-size: 22px;
  border-collapse: collapse;
  width: 100%;
}
th, td {
  border: 1px solid #ccc;
  padding: 15px;
  text-align: left;
}
th {
  background-color: #f4f4f4;
  color: #333;
}
strong {
  color: #0056b3;
}
</style>

# T1047 - WMI

#### Transport protocol

| Protocol | Mechanism | Ports | Offensive Context |
|---|---|---|---|
| **DCOM/RPC** | Legacy WMI transport | TCP 135 (Mapper) & 49152–65535 (Ephemeral) | Blocked by strict firewalls restricting dynamic port ranges. |
| **WinRM** | Modern WS-Man (SOAP/XML) | TCP 5985 (HTTP) & 5986 (HTTPS) | Highly firewall-friendly; heavily abused for lateral movement. |

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

#### Local Process Spawning

* **Using wmic.exe:** Tận dụng cmd line console được cài đặt sẵn (ví dụ câu lệnh: wmic.exe process call create) để proxy việc execution của các binaries.
* **Using PowerShell:** Sử dụng các built-in cmdlets như Invoke-WmiMethod hoặc phiên bản hiện đại hóa Invoke-CimMethod để gọi class Win32_Process.
* **Advantage:** Cả hai phương pháp đều hoạt động như các Living-off-the-Land (LotL) proxies giúp che giấu process lineage. Payload được spawn dưới dạng một child process của WMI Provider Host (WmiPrvSE.exe) thay vì shell, qua đó bypass các cơ chế giám sát tiến trình cha con tiêu chuẩn.

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
table {
  margin-left: auto;
  margin-right: auto;
  margin-top: 30px;
  font-size: 22px;
  border-collapse: collapse;
  width: 100%;
}
th, td {
  border: 1px solid #ccc;
  padding: 15px;
  text-align: left;
}
th {
  background-color: #f4f4f4;
  color: #333;
}
strong {
  color: #0056b3;
}
</style>

# T1047 - WMI

#### Remote Execution & Lateral Movement

| Feature | Remote WMI via DCOM | Remote WMI over WinRM |
|---|---|---|
| **Protocol** | DCOM (DCE/RPC) | WS-Man (HTTP/HTTPS) |
| **Tools** | Impacket's `wmiexec.py` | PowerShell (`New-CimSession`, `Invoke-CimMethod`) |
| **Mechanics** | Interacts with the remote `ISystemActivator` interface | Utilizes modern CIM standard cmdlets |
| **Output Handling** | Wraps payload in `cmd.exe`, redirects output to `ADMIN$` share, and reads via SMB | Executed dynamically without requiring SMB redirection |


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
li li {
  font-size: 24px;
  margin-bottom: 10px;
  line-height: 1.4;
}
strong {
  color: #0056b3;
}
</style>

# T1047 - WMI

#### System Discovery & Reconnaissance

* **WQL Execution:** Attackers use cmdlets như `Get-WmiObject` để thực thi các câu lệnh WMI Query Language (WQL), nhằm enumerate hệ thống và blending in with standard administrative traffic.
* **Some Query Providers:**
  * **Core System (`root\cimv2`):** Extract các hardware info và tiến trình đang hoạt động bằng cách querying các classes như `Win32_Process`.
  * **Security Mapping (`root\SecurityCenter2`):** Trực tiếp query `AntiVirusProduct` để phát hiện các EDR hoặc sản phẩm AV đã được cài đặt.
  * **Active Directory (`root\directory\ldap`):** Extract thông tin về domain users, computers, và group configurations.


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

#### Programmatic / Unmanaged Execution

* **Direct API Interaction:** Bypass các standard command-line interpreters (wmic.exe, PowerShell) bằng cách tương tác trực tiếp với các WMI Component Object Model (COM) APIs thông qua unmanaged code (C++ hoặc .NET).
* **Mechanics:** Malware khởi tạo `IWbemLocator` để kết nối đến `root\cimv2`, sau đó sử dụng `IWbemServices::ExecMethod` để invoke `Win32_Process::Create`.
* **Advantage:** Spawn các payloads hoàn toàn trên bộ nhớ. Bởi vì không có bất kỳ command-line wrapper nào được sử dụng, technique này hoàn toàn bypass Process Creation logging (Event ID 4688).

---
<!-- class: default -->
<!-- _header: "" -->

<style scoped>
.code-snippets {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 10px;
  height: 82vh; /* Limits height to leave room for the caption at the bottom */
  width: 100%;
  margin-top: 10px;
}
.code-snippets img {
  max-width: 32%;
  max-height: 100%;
  object-fit: contain; /* Scales images up while keeping their aspect ratio */
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
  border: 1px solid #ddd;
  border-radius: 4px;
}
.caption {
  text-align: center;
  font-size: 26px;
  margin-top: 15px;
  font-weight: bold;
  color: #333;
}
</style>

<div class="code-snippets">
  <img src="code1.png" />
  <img src="code2.png" />
  <img src="code3.png" />
</div>

<p class="caption">Sample code interacting with WMI COM API</p>

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

#### WmiPrvSE.exe & Defense Evasion

* **Parent-Child Relationship:** Các payload sử dụng WMI phá vỡ execution chain thông thường bằng cách spawn dưới WMI Provider Host (WmiPrvSE.exe) thay vì initiating process, qua đó che giấu process lineage và evade các standard security analytics.
* **Security Product Manipulation:** Bởi vì attackers có thể execute code mà không cần phần mềm thứ 3, họ lạm dụng WMI để ngầm gỡ cài đặt các EDR/AV solutions thông qua class Win32_Product mà không trigger uninstall logs.
* **Event Log Tampering:** Các adversaries thường xuyên target vào class Win32_NTEventlogFile và invoke method ClearEventLog để xóa critical forensic logs trực tiếp thông qua WMI infrastructure.

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
table {
  margin-left: auto;
  margin-right: auto;
  margin-top: 30px;
  font-size: 22px;
  border-collapse: collapse;
  width: 100%;
}
th, td {
  border: 1px solid #ccc;
  padding: 15px;
  text-align: left;
}
th {
  background-color: #f4f4f4;
  color: #333;
}
strong {
  color: #0056b3;
}
code {
  white-space: nowrap;
}
</style>

# T1047 - WMI

#### Standard WMI Logging

| Log Source | Event ID | Description |
|---|---|---|
| **Windows Security** | `Event ID 4688` | Process Creation (identifies `WmiPrvSE.exe` spawning child processes). |
| **Windows Security** | `Event ID 4624` | Logon Type 3 (Network logon during remote WMI execution). |
| **Sysmon** | `Event ID 1` | Process Creation (captures command-line arguments and parent-child lineage). |
| **Sysmon** | `Event ID 19, 20, 21` | WMI Activity (WmiEventFilter, WmiEventConsumer, and Filter-to-Consumer Binding). |


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
  font-size: 22px;
  line-height: 1.6;
  margin-bottom: 20px;
}
table {
  margin-left: auto;
  margin-right: auto;
  margin-top: 20px;
  font-size: 20px;
  border-collapse: collapse;
  width: 100%;
}
th, td {
  border: 1px solid #ccc;
  padding: 15px;
  text-align: left;
}
th {
  background-color: #f4f4f4;
  color: #333;
}
strong {
  color: #0056b3;
}
code {
  white-space: nowrap;
}
</style>

# T1047 - WMI

#### ETW Telemetry

* **ETW Provider:** The Microsoft-Windows-WMI-Activity provider cung cấp nhiều thông tin chi tiết hơn về native WMI execution mà log thông thường không bắt được.

| Channel | Event ID | Telemetry Description |
|---|---|---|
| **Operational** | `5857` | Provider initialization and host startup events. |
| **Operational** | `5858` | Query and method execution errors (flags malformed or failed reconnaissance). |
| **Operational** | `5859, 5860, 5861` | WMI Event Filter, Consumer, and Binding activity (identifies persistence). |
| **Trace** | `11` | Method invocation (captures `Win32_Process::Create`, caller PID, and user context). |

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
li li {
  font-size: 24px;
  margin-bottom: 10px;
  line-height: 1.4;
}
strong {
  color: #0056b3;
}
</style>

# T1047 - WMI

#### Blinding ETW (Defense Evasion)

* **The Telemetry Problem:** Bởi vì ETW cung cấp thông tin chi tiết vào quá trình thực thi các program qua WMI, các attackers tích cực nhắm vào nó để tránh bị phát hiện.
* **Evasion Techniques:**
  * **In-Memory Patching:** Malware locate `ntdll!EtwEventWrite` bên trong memory space của `WmiPrvSE.exe` và ghi đè vài bytes đầu tiên bằng một RET (return) instruction, qua đó lặng lẽ drop nguồn data.
  * **Provider Disabling:** Attackers lạm dụng quyền admin để tắt hoàn toàn logging channel bằng cách sử dụng các công cụ có sẵn (ví dụ: `wevtutil sl Microsoft-Windows-WMI-Activity/Operational /e:false`).