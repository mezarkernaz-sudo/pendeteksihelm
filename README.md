# Dataset Deployment Project

## 📌 Deskripsi Proyek

Proyek ini berisi dataset dan konfigurasi deployment menggunakan dua pendekatan:

1. **Menggunakan Helm** → Deployment Kubernetes yang lebih terstruktur dan reusable.
2. **Tanpa Helm** → Deployment langsung menggunakan file YAML Kubernetes standar.

Tujuan proyek ini adalah membandingkan kemudahan konfigurasi, maintenance, dan deployment antara penggunaan Helm dan deployment manual.

---

# 📂 Struktur Folder

```bash
project-dataset/
│
├── dataset/
│   ├── sample-data.csv
│   └── README.md
│
├── helm/
│   ├── Chart.yaml
│   ├── values.yaml
│   └── templates/
│       ├── deployment.yaml
│       ├── service.yaml
│       └── ingress.yaml
│
├── non-helm/
│   ├── deployment.yaml
│   ├── service.yaml
│   └── ingress.yaml
│
└── README.md
```

---

# 🚀 Deployment Menggunakan Helm

## 📖 Apa itu Helm?

Helm adalah package manager untuk Kubernetes yang mempermudah deployment aplikasi menggunakan template.

## ✅ Keuntungan Helm

* Konfigurasi lebih fleksibel
* Mudah melakukan upgrade dan rollback
* Reusable template
* Management deployment lebih rapi

## 📦 Install Helm

```bash
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
```

## ▶️ Cara Deployment

Masuk ke folder helm:

```bash
cd helm
```

Install chart:

```bash
helm install dataset-app .
```

Cek deployment:

```bash
kubectl get pods
```

Upgrade deployment:

```bash
helm upgrade dataset-app .
```

Uninstall deployment:

```bash
helm uninstall dataset-app
```

---

# 🚀 Deployment Tanpa Helm

## 📖 Penjelasan

Deployment dilakukan langsung menggunakan file YAML Kubernetes.

## ✅ Keuntungan Tanpa Helm

* Lebih sederhana untuk project kecil
* Tidak membutuhkan dependency tambahan
* Mudah dipahami pemula

## ▶️ Cara Deployment

Masuk ke folder non-helm:

```bash
cd non-helm
```

Apply deployment:

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl apply -f ingress.yaml
```

Cek deployment:

```bash
kubectl get all
```

Hapus deployment:

```bash
kubectl delete -f deployment.yaml
kubectl delete -f service.yaml
kubectl delete -f ingress.yaml
```

---

# 📊 Perbandingan Helm vs Non-Helm

| Fitur                 | Helm | Non-Helm |
| --------------------- | ---- | -------- |
| Reusable Template     | ✅    | ❌        |
| Mudah Upgrade         | ✅    | ❌        |
| Cocok Project Besar   | ✅    | ❌        |
| Mudah Dipahami Pemula | ❌    | ✅        |
| Maintenance           | ✅    | ❌        |

---

# 🛠 Requirements

* Kubernetes Cluster
* kubectl
* Helm v3+
* Docker

---

# 📁 Dataset

Dataset berada di folder:

```bash
/dataset
```

Format dataset dapat berupa:

* CSV
* JSON
* Excel

Contoh:

```csv
id,nama,kategori
1,Dataset A,Training
2,Dataset B,Testing
```

---

# 👨‍💻 Author

Nama: mezarkernaz
GitHub:https://mezarkernaz-sudo.github.io/pendeteksihelm/

---

# 📜 License

Project ini menggunakan lisensi MIT.
# pendeteksihelm
