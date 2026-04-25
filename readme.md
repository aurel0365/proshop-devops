# AFL 2 - Scale-Up & Ship: Automating Microservices on Proxmox

<img width="776" height="411" alt="Screenshot 2026-04-25 234509" src="https://github.com/user-attachments/assets/75d18256-e655-4865-bac0-b74d1b35793b" />


## 📌 Overview

Proyek ini merupakan implementasi dari konsep **DevOps end-to-end automation pipeline** yang bertujuan untuk mengubah proses deployment aplikasi microservices dari sistem manual menjadi sistem yang sepenuhnya otomatis.

Dalam skenario ini, sebuah startup fiktif bernama **DevOps Solutions Corp** mengalami masalah dalam proses deployment aplikasi karena masih dilakukan secara manual, mulai dari provisioning server, konfigurasi environment, hingga deployment aplikasi.

Oleh karena itu, solusi yang dibangun dalam proyek ini adalah sebuah pipeline otomatis yang menghubungkan:

- Version Control (GitHub)
- Infrastructure as Code (Terraform + Proxmox)
- Configuration Management (Ansible)
- Containerization (Docker & Docker Compose)
- CI/CD Pipeline (Jenkins)

---

## 🎯 Tujuan Proyek

Tujuan utama dari proyek ini adalah:

- Mengotomatisasi proses deployment aplikasi berbasis microservices
- Meningkatkan konsistensi environment antara development dan production
- Mengurangi human error dalam provisioning dan konfigurasi server
- Menerapkan prinsip DevOps modern dalam satu pipeline terintegrasi
- Membuat sistem yang scalable dan siap untuk pengembangan lebih lanjut (misalnya Kubernetes)

---

## 🧠 Konsep Utama yang Diterapkan

### 1. GitHub sebagai Single Source of Truth
Semua kode aplikasi dan konfigurasi disimpan di GitHub sebagai pusat kendali utama. Setiap perubahan kode akan menjadi pemicu proses CI/CD.

📌 **Konsep:** Version control dan collaboration

---

### 2. Infrastructure as Code (Terraform + Proxmox)
Infrastruktur server tidak dibuat secara manual, tetapi didefinisikan dalam bentuk kode menggunakan Terraform.

📌 **Konsep:** Reproducible infrastructure  
Artinya, server dapat dibuat ulang dengan konfigurasi yang sama kapan saja tanpa perbedaan.

---

### 3. Configuration Management (Ansible)
Setelah server dibuat, konfigurasi seperti instalasi Docker dan dependency dilakukan secara otomatis menggunakan Ansible melalui SSH.

📌 **Konsep:** Agentless automation  
Tidak membutuhkan instalasi software tambahan di server target.

---

### 4. Containerization (Docker & Docker Compose)
Aplikasi dijalankan dalam container agar environment selalu konsisten di semua sistem.

- `item-app` → aplikasi backend/frontend
- `item-db` → database MongoDB

📌 **Konsep:** Isolated and portable environment

---

### 5. CI/CD Pipeline (Jenkins)
Jenkins digunakan untuk mengotomatisasi proses:

- Build aplikasi
- Testing otomatis
- Deployment ke server

Pipeline ini berjalan setiap kali ada perubahan di GitHub.

📌 **Konsep:** Continuous Integration & Continuous Deployment

---

## 🔄 Alur Workflow Sistem

Secara sederhana, alur kerja sistem adalah:

1. Developer melakukan push code ke GitHub  
2. Jenkins mendeteksi perubahan dan menjalankan pipeline  
3. Aplikasi di-build menjadi Docker image  
4. Testing dijalankan untuk memastikan aplikasi berjalan  
5. Aplikasi di-deploy ke server Proxmox (via Ansible)  
6. Aplikasi berjalan dalam container Docker

---

## 📈 Manfaat Implementasi

Dengan pendekatan ini, beberapa manfaat yang diperoleh adalah:

- Deployment lebih cepat dan otomatis
- Mengurangi kesalahan konfigurasi manual
- Infrastruktur lebih mudah direplikasi
- Proses pengembangan lebih efisien
- Siap untuk scale ke arsitektur lebih besar (microservices/Kubernetes)

---

## 🧩 Kesimpulan

Proyek ini menunjukkan implementasi nyata dari prinsip **DevOps lifecycle**, di mana development, operations, dan automation digabungkan dalam satu sistem yang saling terintegrasi.

Dengan pipeline ini, seluruh proses dari kode hingga deployment dapat berjalan secara otomatis, konsisten, dan dapat diandalkan.

---
