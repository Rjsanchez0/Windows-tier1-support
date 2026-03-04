# Windows Tier 1 Support Lab Notes (with Ticket Walkthrough)

This repository converts my Notion study notes into a GitHub-ready portfolio piece. It demonstrates practical **Tier 1 / service desk** tasks in Windows, with a sample ticket and step-by-step documentation.

## What this shows (skills)
- Local user administration (create users, set password options, local admin group membership)
- Basic **access control** and local file permissions (inheritance, restricting access)
- Windows maintenance fundamentals (updates, active hours)
- Troubleshooting foundations (Event Viewer, Task Manager, basic CMD networking commands)
- Task automation basics (Task Scheduler + creating a scheduled disk cleanup)
- Clear, repeatable documentation suitable for a KB / runbook

## Lab environment
- Windows 10/11 workstation (local accounts)
- Built-in Windows tools: **lusrmgr.msc**, File Explorer Security tab, Windows Update, Event Viewer, Task Manager, Task Scheduler, Command Prompt
- Documentation captured with screenshots and written steps

---

## 1) Administering local user accounts

**Goal:** Manage local users and groups using the GUI.

![Local Users and Groups](images/01_local_users_groups_overview.png)

You can open the Local Users and Groups console via `Run`:

![Run lusrmgr](images/02_run_lusrmgr_command.png)

![Local Users and Groups GUI](images/03_local_users_groups_gui.png)

### Local admin vs standard user
Local administrators can manage apps/drivers, system settings, and other users on the machine.

![Local admin privileges](images/04_local_admin_privileges.png)

Adding a user to the **Administrators** group grants elevated privileges.

![Admin group permissions](images/05_admin_group_permissions.png)

---

## 2) Creating a local user (Tier 1 workflow)

Right-click **Users** → **New User**:

![New user menu](images/06_new_user_menu.png)

Fill out user details and password requirements:

![New user form](images/07_new_user_form.png)

Add the new account to the local **Administrators** group if the ticket/request requires it:

![Add user to admin group](images/08_add_user_to_admin_group.png)

Common account actions include setting/resetting passwords, renaming, or deleting the account:

![Account actions](images/09_user_account_actions.png)

---

## 3) Sample Service Desk Ticket Walkthrough

### Ticket #44521 — Add local user and grant admin access
**Request:** Create a local user **James**, require password change at first login, and add to local administrators.

![Ticket request](images/10_ticket_44521_request.png)

**Resolution steps:**
1. Log in as an admin user.
2. Open **Local Users and Groups** (`lusrmgr.msc`).
3. Create the user and set the “change password at next logon” option.
4. Adjust group membership to add the user to **Administrators**.

![Open lusrmgr](images/11_open_lusrmgr_ticket_step.png)

![Create user](images/12_create_user_ticket_step.png)

**Close-out notes example (what I’d put in the ticket):**
- Created local user `James`
- Set password to require change at first logon
- Added `James` to local **Administrators**
- Verified login prompt and group membership

---

## 4) Local file permissions (access control fundamentals)

![File permissions overview](images/13_file_permissions_overview.png)

Create a folder (example: `test folder`):

![Create folder](images/14_create_test_folder.png)

By default, inherited permissions can allow other users to read/modify depending on the parent folder’s ACLs:

![Default permissions](images/15_default_folder_permissions.png)

To customize access, remove inherited permissions:

![Remove inheritance](images/16_remove_inherited_permissions.png)

Restrict to **Admin only** (example):

![Admin only permissions](images/17_admin_only_permissions.png)

Verify standard user access is blocked:

![User denied](images/18_user_access_denied.png)

---

## 5) Windows updates (maintenance + troubleshooting readiness)

Windows Update settings and update cadence basics:

![Windows Update](images/19_windows_update_settings.png)

If an update causes issues, you can uninstall it and use recovery options when needed:

![Uninstall updates / recovery](images/20_uninstall_update_recovery.png)

Set **Active Hours** to prevent restarts during working hours:

![Active hours](images/21_active_hours.png)

---

## 6) Event Viewer and Task Manager (first-line troubleshooting)

Event Viewer helps identify errors and correlate issues by time:

![Event Viewer](images/22_event_viewer_overview.png)

Application logs can be filtered to pinpoint crashes or recurring errors:

![Application logs](images/23_event_viewer_app_logs.png)

Task Manager shows resource usage and allows ending unresponsive tasks:

![Task Manager](images/24_task_manager_processes.png)

---

## 7) Basic Windows CMD commands (connectivity checks)

```text
cd            # change directory
cd ..         # move up one directory
ipconfig      # view network configuration
/?            # show help for many commands
ping <host>   # test connectivity to a host/IP
```

---

## 8) Task Scheduler (basic automation)

Task Scheduler shows scheduled tasks on the system:

![Task Scheduler](images/25_task_scheduler_overview.png)

Example: Creating a scheduled **Disk Cleanup** task:

![Create task step 1](images/26_create_task_step1.png)
![Create task step 2](images/27_create_task_step2.png)
![Create task step 3](images/28_create_task_step3.png)
![Create task step 4](images/29_create_task_step4.png)

---

## Lessons learned
- Clear documentation matters: a good ticket close-out includes **what changed**, **where**, and **how it was verified**.
- Permissions should be intentional: understand inheritance before changing ACLs.
- Event Viewer + Task Manager are fast wins for Tier 1 triage.


