## 📘 RHCSA Study Notes: Chapters 5–7 (RHEL 8)

Author: Siyabonga Mkhwanazi  
Course: RH124 - Red Hat Certified System Administrator (RHEL 8) 

---

### ✅ Chapter 5: Creating, Viewing, and Editing Text Files

#### 🔹 Standard Output and Error

- **stdout (1)**: Normal output
- **stderr (2)**: Error output

#### 🔹 Output Redirection Examples

| Command                        | Description                                                   |
|-------------------------------|---------------------------------------------------------------|
| `> file`                      | Redirects stdout to a file (overwrites)                       |
| `>> file`                     | Appends stdout to a file                                      |
| `2> file`                     | Redirects stderr to a file                                    |
| `&> file`                     | Redirects both stdout and stderr to a file                    |
| `2>/dev/null`                 | Hides errors                                                  |
| `> file 2>file2`              | Redirects stdout to file, stderr to file2                     |
| `>> file 2>&1`                | Appends both stdout and stderr to a file                      |
| `command | tee file`          | Outputs to screen and saves to file                           |

#### 🔹 Practice Commands

```bash
ls /etc /fake 2>/dev/null         # Suppresses error for invalid path
ls /etc /fake &> both.txt         # Saves both stdout and stderr to file
echo "Hello" | tee hello.txt      # Outputs and saves to file
```

---

### ✅ Chapter 6: Managing Local Users and Groups

#### 🔹 User Management

| Command                                      | Description                            |
|---------------------------------------------|----------------------------------------|
| `useradd username`                          | Creates a new user                     |
| `passwd username`                           | Sets or changes the password           |
| `userdel username`                          | Deletes user (keeps home dir)          |
| `userdel -r username`                       | Deletes user and home dir              |
| `usermod -aG group username`                | Adds user to a group                   |
| `id username`                               | Shows UID, GID, and group membership   |
| `groups username`                           | Lists groups user belongs to           |

#### 🔹 Group Management

| Command                        | Description                     |
|--------------------------------|---------------------------------|
| `groupadd groupname`           | Creates a new group             |
| `groupdel groupname`           | Deletes a group                 |
| `groupmod -n new old`          | Renames a group                 |

#### 🔹 Files

- **`/etc/passwd`** – User account information
- **`/etc/group`** – Group membership
- **`/etc/shadow`** – Encrypted passwords

#### 🔹 Sudo Access

```bash
usermod -aG wheel username    # Grants sudo privileges on RHEL-based systems
```

---

### ✅ Chapter 7: Controlling Access to Files

#### 🔹 File Permission Structure

```bash
-rwxr-xr-- 1 user group file
```

- 1st char: File type (`-` = file, `d` = directory)
- Next 3: Owner permissions (rwx)
- Next 3: Group permissions (r-x)
- Final 3: Others permissions (r--)

#### 🔹 Permission Values

| Symbol | Value | Meaning  |
|--------|-------|----------|
| `r`    | 4     | Read     |
| `w`    | 2     | Write    |
| `x`    | 1     | Execute  |

#### 🔹 Changing Permissions

```bash
chmod 755 file            # rwxr-xr-x
chmod u+x file            # Add execute to user
chmod g-w file            # Remove write from group
```

#### 🔹 Changing Ownership

```bash
chown user:group file
```

#### 🔹 Special Note: Deletion

To delete a file, you need write **permission on the directory**, not the file itself.

#### 🔹 Practice Example

```bash
# Create test file
touch file1
chmod 764 file1
chown siya:developers file1

# View
ls -l file1
```

---

## 🧪 Practice Lab Scenarios

1. **Create a user and grant sudo:**
   ```bash
   useradd devadmin
   passwd devadmin
   usermod -aG wheel devadmin
   ```

2. **Redirect errors and output:**
   ```bash
   ls /etc /fake 2>/dev/null
   ls /etc /fake &>output.txt
   ```

3. **Permissions:**
   ```bash
   touch secure.txt
   chmod 640 secure.txt
   chown root:wheel secure.txt
   ```

---
