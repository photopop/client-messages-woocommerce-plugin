# Client Messages (Spjaet)

**Version:** 1.3.7-EN
**Author:** Runólfur Guðbjörnsson

A custom-built WordPress plugin designed to deliver targeted messages to customers directly in their WooCommerce "My Account" area. It solves problems with unreliable email delivery by creating an internal "bulletin board" system.

---

## 🚀 Key Features

### Admin Panel (Backend)
* **Central Message Management:** Creates a new admin menu item, "Client Messages", where all messages can be created and managed.
* **Precise Targeting:** Each message can be targeted based on one of three methods:
    1.  **Subscription Status:** (e.g., `Active`, `On-hold`, `Pending`). Multiple statuses can be selected.
    2.  **Product (Team) ID:** Targets all customers with a subscription to a specific product ID.
    3.  **Customer ID:** Targets a single, specific customer via their user ID.
* **Admin Overview:** A new "Targeting" column in the message list clearly shows how each message is targeted (e.g., "Customer: John Doe (ID: 2)").
* **Notification Management:** A "Receive Emails" checkbox is added to all user profiles in the admin panel for admin control.

### Customer Side (Frontend)
* **New "My Account" Tab:** Adds a "Messages" tab to the WooCommerce "My Account" menu.
* **Dynamic Content:** Customers *only* see the messages they are targeted for.
* **"Read More" Function:** Long messages (over 55 words) are automatically truncated with a "Read more..." button to keep the page clean and scannable.
* **Notification Self-service:** Customers can opt-out of email notifications via a checkbox on their "Account Details" page.

### Email Notifications
* **Automatic Dispatch:** When a *new* message is published, an email notification is triggered.
* **Asynchronous (WP-Cron):** The email dispatch is run in the background (using `wp_schedule_single_event`) to prevent the admin panel from freezing or timing out when sending to many customers.
* **Respects Opt-out:** Only sends emails to customers who have *not* actively opted out. The default setting is "opt-in" for all users.

---

## 🔧 Installation

1.  Download the latest version as a `.zip` file from this repository (via "Code" -> "Download ZIP").
2.  In your WordPress admin panel, go to **Plugins -> Add New -> Upload Plugin**.
3.  Select the `.zip` file and click "Install Now".
4.  **Important:** Once the plugin is installed, you must **Deactivate** it and then **Re-activate** it. This is necessary to register the new "Messages" page endpoint (`/my-account/messages/`) and avoid 404 errors.
