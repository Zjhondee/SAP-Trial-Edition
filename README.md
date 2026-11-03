
SAP NetWeaver AS ABAP 7.52 &Security Home Lab

# SAP Basis & Security Home Lab Portfolio

## System Architecture & Overview
- **Core System:** SAP NetWeaver AS ABAP 7.52 Developer Edition
- **Database:** Sybase ASE 16
- **Operating System:** openSUSE Leap (Host environment: Oracle VirtualBox)
- **Frontend:** SAP GUI for Windows / SAP Logon

---

## 1. Installation & Environment Configuration
Detailed documentation of OS prerequisite preparation, network host mapping, VirtualBox setup, and SAP GUI connectivity.

### Key Deployment Troubleshooting
- **Swap Space Allocation:** Resolved installation memory failure by expanding swap space on openSUSE.
- **Directory Permissions:** Resolved Sybase license errors by reconfiguring directory ownership and permissions (`chown`/`chmod`).

---

## 2. Core Basis Administration & Operations
- **Service Management:** Execution of `startsap`, `stopsap`, and `sapcontrol`.
<img width="813" height="580" alt="image" src="https://github.com/user-attachments/assets/ffa5aaf7-2107-4bef-8b9d-4a5970a22d32" />
<img width="732" height="364" alt="image" src="https://github.com/user-attachments/assets/a3fa8a35-3b6b-47dd-a76f-62cc3a65be32" />

- **Database Connectivity:** Verification via `R3trans -d` (handling return codes rc=0000 to 0012).
  <img width="540" height="75" alt="image" src="https://github.com/user-attachments/assets/9d13f8cf-6809-420b-a68a-7279861b08da" />

- **Post-Install Verification:** System consistency checks using T-Code `SICK` and license management with `SLICENSE`.
 <img width="946" height="346" alt="image" src="https://github.com/user-attachments/assets/970edf83-4099-41a2-9700-864b5284acb8" />
<img width="527" height="161" alt="image" src="https://github.com/user-attachments/assets/619147b6-2697-4faf-b876-c5818b0311d1" />
<img width="629" height="358" alt="image" src="https://github.com/user-attachments/assets/6f807dfd-de6d-45cc-80da-763d39e5df09" />

- **System Maintenance:** Parameter updates (`RZ10`, `RZ11`), background job scheduling (`SM36`, `SM37`), and client management (`SCC4`).
<img width="603" height="164" alt="image" src="https://github.com/user-attachments/assets/0ff15420-0ff2-4768-bb72-a482f81ebce3" />

- **Client Copying:** Creation of client ID (100) using T-Code `SCC4`, local client copy with `SCCL`, log monitoring via `SCC3`, logical system definition in `BD54`, system conversion using `BDLS`, BP index regeneration via `BUSP`, and outbound email management with `SOST`
<img width="967" height="938" alt="image" src="https://github.com/user-attachments/assets/b53a06a3-c0ca-4939-af07-ba7cb8cf3e37" />
<img width="1001" height="937" alt="image" src="https://github.com/user-attachments/assets/d46b6ffb-168d-4ea1-ad89-22bf663aed5d" />
<img width="1008" height="265" alt="image" src="https://github.com/user-attachments/assets/83e7ac77-f360-4c8d-98fd-5ddfc5fd93cf" />
<img width="1009" height="595" alt="image" src="https://github.com/user-attachments/assets/71f05b2b-9a06-4c1a-9886-85fe18ea84c7" />
<img width="1010" height="236" alt="image" src="https://github.com/user-attachments/assets/d6d3bfad-5829-4195-adfd-0896a82a4eac" />
<img width="1011" height="487" alt="image" src="https://github.com/user-attachments/assets/819d2803-456a-4203-a41c-b5a5cb0e46b7" />
<img width="1034" height="389" alt="image" src="https://github.com/user-attachments/assets/8c4353b3-df9d-478a-845e-9001e71f2489" />
<img width="922" height="654" alt="image" src="https://github.com/user-attachments/assets/5aa606a6-75a9-4dc6-93f3-b4aa2c925755" />
<img width="1005" height="936" alt="image" src="https://github.com/user-attachments/assets/5bec5c6a-5b9d-42ce-ab91-de59b6281569" />
<img width="1013" height="938" alt="image" src="https://github.com/user-attachments/assets/82294435-4295-4560-b05e-196e8465b231" />
<img width="922" height="654" alt="image" src="https://github.com/user-attachments/assets/3443d450-0e99-4b66-9e06-5b08535dca46" />
<img width="1001" height="939" alt="image" src="https://github.com/user-attachments/assets/8af995f7-986b-4103-972e-121537f509f6" />
<img width="1005" height="936" alt="image" src="https://github.com/user-attachments/assets/2d75858e-73f4-4930-a8c9-994adcc6b049" />

<img width="641" height="733" alt="image" src="https://github.com/user-attachments/assets/9ceb5ca5-991b-4d9f-9f61-c3afa11d5cdf" />
---

## 3. Daily System Health-Check Routine (Client 001)
Execution sequence for daily system monitoring:
1. `ST22` – ABAP Dump Analysis
   <img width="1135" height="190" alt="image" src="https://github.com/user-attachments/assets/58238d58-a06b-4deb-871c-d874256350d6" />

2. `RZ20` – CCMS Alert Monitoring
   <img width="1177" height="940" alt="image" src="https://github.com/user-attachments/assets/913a4fd3-e922-4968-a766-3a82beb4ac5b" />

4. `SM13` – Update Record Verification
   <img width="488" height="533" alt="image" src="https://github.com/user-attachments/assets/a525eebc-a498-44df-a757-7300a8543d5c" />
   <img width="856" height="297" alt="image" src="https://github.com/user-attachments/assets/c8e2f696-f245-4507-ab69-d2aca79a9323" />
5. `SMQ2` – Outbound Queue Monitoring
   <img width="438" height="204" alt="image" src="https://github.com/user-attachments/assets/7be1bf62-fd7b-4a6b-b506-e2e44e719012" />
   <img width="587" height="263" alt="image" src="https://github.com/user-attachments/assets/0ace30f1-803f-47a3-abc3-811936190fc4" />

7. `SMLG` – Logon Group Balance Check
   <img width="738" height="245" alt="image" src="https://github.com/user-attachments/assets/8dc4f271-230d-4dc5-abb9-0984000cfc78" />
   <img width="286" height="334" alt="image" src="https://github.com/user-attachments/assets/68ca4de3-2300-4d1c-9263-07f65eed169a" />

9. `SM50` / `SM66` – Active Work Process Monitoring
<img width="1133" height="354" alt="image" src="https://github.com/user-attachments/assets/b4e93665-3ad9-4d9d-9e2b-97c33908e372" />
<img width="1136" height="464" alt="image" src="https://github.com/user-attachments/assets/69359dd3-c1d1-489f-84b8-81a53df4f1ca" />
<img width="1693" height="208" alt="image" src="https://github.com/user-attachments/assets/0e42178d-7cd1-4dfd-aafc-c875741b3742" />

---

## 4. Security, User Administration & Authorizations
- **User Master Maintenance:** Individual user creation and management (`SU01`).
  <img width="1025" height="40" alt="image" src="https://github.com/user-attachments/assets/d861a360-65d1-4461-be07-9f674b4985cd" />
- **Role Maintenance:** Authorization role building, profile adjustments, and authorizations tracing (`PFCG`).
- **Profile Generator Setup:** Initialization of standard system authorization tables (`SU25` Step 1).
  <img width="614" height="536" alt="image" src="https://github.com/user-attachments/assets/74048a32-1b4f-452a-85ff-aaecc4851b18" />

