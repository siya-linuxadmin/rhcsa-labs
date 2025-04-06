# 🔐 Granting Sudo Access to a New Linux User

This lab demonstrates how to securely create a new user on a RHEL system and grant them administrative privileges using the `/etc/sudoers.d/` method. It includes lessons learned, screenshots, and real terminal output captured in MobaXterm.

---

## ✅ Objective

- Create a new Linux user account
- Grant the user sudo privileges safely
- Avoid common mistakes (like invalid sudoers syntax)
- Document the process with screenshots and explanation

---

## 🧑‍💻 Steps Performed

### 1. Switched to root user
```bash
sudo -i
useradd -m jesus
visudo -f /etc/sudoers.d/jesus
jesus    ALL=(ALL)       ALL
su - jesus
sudo whoami
# Output: root
su - siya
su: user siya does not exist
useradd -m siya
visudo -f /etc/sudoers.d/siya
siya    ALL=(ALL)       ALL

![Switching to root](./sudo-i.png)
![Creating user](./useradd-jesus.png)
![Visudo sudoers file](./visudo-jesus.png)
![Sudo verification](./sudo-whoami.png)

---

## 💡 Lessons Learned

- `visudo` is safer than editing `/etc/sudoers` directly.
- Entries with incorrect spacing or formatting will cause errors (e.g., `abdul j`).
- Every user added for sudo access should have a separate file under `/etc/sudoers.d/` for clean management.

---

## 👤 Author

**Siyabonga Mkhwanazi**  
🔗 [LinkedIn](https://www.linkedin.com/in/siyabonga-mkhwanazi-99486b108)  
📂 [GitHub](https://github.com/siya-linuxadmin)
