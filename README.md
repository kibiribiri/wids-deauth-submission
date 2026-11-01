# WIDS Submission: Code and A1 Poster

Author: Ted Kamau

This repository contains my submission for the wireless intrusion detection
system (WIDS) assignment.

## Files

- `WIDS_Ted_Kamau.zip`: code, prepared data, trained model, results and poster.
- `WIDS_Poster_Ted_Kamau.pdf`: A1 poster.
- `DESCRIPTION.txt`: short description of every file in the zip.

## Dataset

WPA3 Attacks Dataset, Deauthentication attack capture.
DOI: 10.17632/cxx5t5nw7z.3, CC BY 4.0.

## What it does

The prototype reads 802.11 captures, builds per-second features for each MAC
address and uses a Random Forest to detect deauthentication floods. When it
finds a flood it raises an alert with the MAC address, time, deauth rate, RSSI
and model score. It is a WIDS only. It does not block traffic.

## Results

Held-out test set: 719 windows (607 normal, 112 attack).

- Accuracy: 100.0%
- Precision: 100.0%
- Recall: 100.0%
- F1: 100.0%
- Confusion matrix: TN 607, FP 0, FN 0, TP 112

The normal demo gives 0 alerts. The attack demo gives 2 alerts.

## How to run

```bash
unzip WIDS_Ted_Kamau.zip
cd WIDS_Ted_Kamau
python3 -m venv .venv
.venv/bin/pip install -r requirements.txt
.venv/bin/python detect.py --pcap data/demo_normal.pcap
.venv/bin/python detect.py --pcap data/demo_attack.pcap
```

See `DESCRIPTION.txt` and the `README.md` inside the zip for the full setup and
the dataset download instructions.

## Source repository

https://github.com/kibiribiri/wids-deauth-detector
