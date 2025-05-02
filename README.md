# kdb+tick

A reference implementation of a vanilla **tickerplant** and **RDB (real-time database)** for use with [kdb+](https://kx.com/kdbplus/). These scripts are commonly used as building blocks in real-time market data capture systems.

Originally published at `code.kx.com/wsvn/kx/kdb+tick`, the following files are included:

## 📄 Included Files

| File         | Description                                            |
|--------------|--------------------------------------------------------|
| `tick.q`     | Tickerplant script that ingests, logs, and publishes updates. |
| `tick/u.q`   | Pub/sub helper script used by `tick.q`.               |
| `tick/r.q`   | Real-time database (RDB) script to subscribe to and persist updates. |

For more information, visit the [official kdb+ documentation](https://code.kx.com/q/).

---

## 🔗 Usage

Run the tickerplant with:

```bash
q tick.q sym . -p 5001 </dev/null >tp.log 2>&1 &
```

Then start the RDB with:

```bash
q tick/r.q -p 5002 </dev/null >rdb.log 2>&1 &
```

And a subscriber or feed can connect to port 5001 and publish updates via the `.u.upd` interface.

---

## 🔒 Hot-Linking Warning

You are welcome to download and use this code under the terms of the license provided.

However, **Kx Systems strongly recommends against hot-linking** (i.e., linking your application directly to this repository) because:

- This is **not a high-availability hosting service**
- Future updates may **break your application**
- Refactoring or file changes may lead to **404 errors**

---

## ✅ Best Practice

> **Download the code** and place it under your own version control.  
> Include it in your application’s regression test suite to ensure continued compatibility.

---

## 📦 Versioning

This repository contains stable snapshots used by the broader kdb+ community. For more robust, production-grade environments, consider:

- Implementing custom logging or compression
- Adding fault-tolerance / HA recovery
- Using [kdb Insights](https://kx.com/insights/) for managed solutions

---

## 📜 License

Use of this code is subject to the Kx licensing agreement. Please refer to the original distribution for licensing terms.

---
