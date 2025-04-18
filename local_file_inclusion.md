
## 🧩 Challenge Resolution

I started by inspecting the web application and its different visible elements. I explored the various pages accessible via the source code (view-source).

### 🔍 Initial Attempts:

- I noticed that the application used a URL structure like `index.php?page=`, which immediately made me think of a possible **Local File Inclusion (LFI)** vulnerability.

### 🧪 Path Testing:

- I tested the inclusion of system files by modifying the `page` parameter to point to local paths.
- Using classic payloads such as:

```
?page=../../../../../../../../etc/passwd
```

---

### 🏁 Conclusion:

The challenge was based on a **LFI vulnerability** caused by improper handling of the `page` parameter. By exploiting this weakness, it would have been possible to freely read files on the server.

---

✅ **Type of vulnerability**: Local File Inclusion (LFI)  
🎯 **Payload used**: `?page=../../../../../../../../etc/passwd`  
🏴 **Result**: b12c4b2cb8094750ae121a676269aa9e2872d07c06e429d25a63196ec1c8c1d0

![Capture d’écran 2025-04-13 à 16 27 13](https://github.com/user-attachments/assets/a5fb0e05-432e-4ab6-801c-afbbd55a80b4)
![Capture d’écran 2025-04-13 à 16 47 51](https://github.com/user-attachments/assets/668cf46e-0f45-41e2-b209-c6cfd9cd9d8d)

