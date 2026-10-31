# Dataset Pemrosesan Citra - Perkuliahan

Berkas pada repository ini dipakai oleh notebook perkuliahan agar input gambar tidak bergantung pada path lokal.

## Struktur

- `minggu_2/citra_latihan_bab3.png`: citra RGB yang dibuat untuk latihan Bab 3.
- `minggu_2/hasil_kanal_rgb.png`: hasil pemisahan kanal RGB pada latihan Bab 3.
- `Pemrosesan Citra/Minggu 2/kucing.jpeg`: gambar kucing untuk latihan Bab 4.
- `Pemrosesan Citra/Minggu 5/DepartmentStore.jpg`: citra demo Wally dari paket Mahotas untuk latihan pencarian pola Bab 5.

Notebook dapat mengakses berkas melalui URL raw, misalnya:

```text
https://raw.githubusercontent.com/GuppyWasShot/datasets_untuk_kuliah/main/minggu_2/citra_latihan_bab3.png
```

Untuk gambar Bab 4:

```text
https://raw.githubusercontent.com/GuppyWasShot/datasets_untuk_kuliah/main/Pemrosesan%20Citra/Minggu%202/kucing.jpeg
```

Untuk citra demo Bab 5:

```text
https://raw.githubusercontent.com/GuppyWasShot/datasets_untuk_kuliah/main/Pemrosesan%20Citra/Minggu%205/DepartmentStore.jpg
```

`DepartmentStore.jpg` disalin dari citra demo yang disertakan dalam [Mahotas](https://github.com/luispedro/mahotas) (`mahotas.demos.load('Wally')`).

## PJBL Viskom Citra: FER-2013

- `PJBL Viskom Citra/FER-2013.zip`: dataset FER-2013 versi gambar (61 MB, 35.887 citra JPG grayscale 48×48 piksel, 7 kelas).

Isi zip:

| Kelas | `train/` | `test/` |
|---|---:|---:|
| angry | 3.995 | 958 |
| disgust | 436 | 111 |
| fear | 4.097 | 1.024 |
| happy | 7.215 | 1.774 |
| neutral | 4.965 | 1.233 |
| sad | 4.830 | 1.247 |
| surprise | 3.171 | 831 |
| **Total** | **28.709** | **7.178** |

SHA-256: `9f3422c7a45b676c2965ef4fc5f3099932aa98fd13eaaa2c254f620a9894a6e9`

Dataset disimpan sebagai satu berkas zip (bukan 35.887 berkas terpisah) dan tidak memakai Git LFS, sehingga bisa diunduh langsung lewat URL raw:

```text
https://raw.githubusercontent.com/GuppyWasShot/datasets_untuk_kuliah/main/PJBL%20Viskom%20Citra/FER-2013.zip
```

Sel untuk notebook (Google Colab maupun lokal):

```python
import os, zipfile, urllib.request

URL = "https://raw.githubusercontent.com/GuppyWasShot/datasets_untuk_kuliah/main/PJBL%20Viskom%20Citra/FER-2013.zip"
DATA_DIR = "FER-2013"

if not os.path.isdir(os.path.join(DATA_DIR, "train")):
    urllib.request.urlretrieve(URL, "FER-2013.zip")
    with zipfile.ZipFile("FER-2013.zip") as zf:
        zf.extractall(DATA_DIR)

TRAIN_DIR = os.path.join(DATA_DIR, "train")
TEST_DIR = os.path.join(DATA_DIR, "test")
```

Sumber: FER-2013 dari ICML 2013 Challenges in Representation Learning (Goodfellow dkk., 2013), versi folder gambar yang beredar di Kaggle.
