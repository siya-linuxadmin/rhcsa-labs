## 🐧 **RHCSA Key Highlights (April 5th):**

### 🌐 **IP Addressing Basics**
- Understanding how IP addresses function is crucial for networking tasks in Linux.
- IP configurations can be managed using commands like `ip addr` or `nmcli`.

---

## 👥 **Users and Groups Management**

### 🔑 **User Types & UID Ranges:**
| Type          | UID Range | Purpose                             |
|---------------|-----------|-------------------------------------|
| Root          | 0         | Superuser, full system control      |
| System Users  | 1–999     | Associated with services            |
| Regular Users | 1000+     | Normal human users                  |

### 📂 **Important Files:**
- **`/etc/passwd`** – Contains user information (username, UID, GID, home directory, shell).
- **`/etc/group`** – Stores group definitions and members.
- **`/etc/shadow`** – Holds encrypted passwords (secured).

### ⚙️ **Essential User Management Commands:**
| Command                            | Action                                            |
|------------------------------------|---------------------------------------------------|
| `useradd username`                 | Create a new user                                 |
| `passwd username`                  | Set user password                                 |
| `id username`                      | Display user's UID, GID, and groups               |
| `groups username`                  | View groups user belongs to                       |
| `usermod -aG groupname username`   | Add user to group (append without removal) ⚠️     |
| `groupadd groupname`               | Create new group                                  |

**⚠️ Remember**:  
`usermod -G groupname username` removes the user from all groups not explicitly listed.  
Use `-aG` to append without removing existing groups.

### 📌 **Group Types:**
- **Primary Group**: Automatically assigned at user creation.
- **Supplemental Groups**: Additional groups assigned later.

---

## ✏️ **Mastering vi/vim Editor:**

### 🎯 **Vim Modes:**
| Mode          | How to Enter | Purpose                          |
|---------------|--------------|----------------------------------|
| Normal Mode   | `Esc`        | Navigation, editing commands     |
| Insert Mode   | `i`, `a`, `o`| Insert text                      |
| Visual Mode   | `v`          | Highlight/select text            |
| Command Mode  | `:`          | Save, quit, search               |

### 📌 **Common vim Commands:**
| Command | Description                          |
|---------|--------------------------------------|
| `i`     | Insert before cursor                 |
| `Esc`   | Return to Normal mode                |
| `:w`    | Save                                 |
| `:q`    | Quit                                 |
| `:wq`   | Save and quit                        |
| `dd`    | Delete entire line                   |
| `yy`    | Yank (copy) current line             |
| `p`     | Paste copied text                    |
| `x`/`dl`| Delete single character              |
| `v`     | Enter visual selection mode          |
| `/text` | Search within file                   |

**🔑 Key Tip**: Always press `Esc` to safely return to Normal Mode before using commands.

---

## 📁 **File Creation & Editing:**
| Command              | Purpose                                |
|----------------------|----------------------------------------|
| `touch filename.txt` | Safely creates empty file              |
| `vim filename.txt`   | Opens or creates file for editing      |
| `cat filename.txt`   | Displays contents of file              |
| `ls -l`              | Lists files with detailed permissions  |

**Best Practice**:  
Use `touch` first to create files, ensuring they exist before editing.

---

## 💻 **Working with MobaXterm:**
- Efficiently SSH into Linux VMs hosted on vCenter.
- Provides a convenient GUI interface for managing remote Linux environments.
- Great for editing files remotely with vim and viewing outputs.

---

## 🧠 **Final Takeaways:**
- Always double-check group modifications with `usermod -aG`.
- Mastery of vim significantly speeds up file editing and system management.
- Practice consistently with file management and user/group operations to build confidence.
- MobaXterm is a powerful and intuitive tool for systems administration.

---

### 📚 **Recommended Next Steps:**
- Practice using `usermod`, `useradd`, and managing file permissions regularly.
- Experiment further with advanced vim commands like macros and buffers.
- Regularly SSH into VMs using MobaXterm to strengthen comfort and familiarity.

Great job today—keep it up! 🎯
