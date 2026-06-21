<div align="center">

# 🆘 ReliefTrack

### A Java-based desktop application to manage and streamline the distribution of essential supplies during disaster situations.

<br/>

![Java](https://img.shields.io/badge/Java-8%2B-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Swing](https://img.shields.io/badge/GUI-Java%20Swing-4A90D9?style=for-the-badge&logo=java&logoColor=white)
![MySQL](https://img.shields.io/badge/Database-MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![JDBC](https://img.shields.io/badge/Connectivity-JDBC-00758F?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Stable-brightgreen?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-lightgrey?style=for-the-badge)

<br/>


</div>

---

## 📌 Overview

When disasters strike, coordinated response saves lives. **ReliefTrack** helps authorities and relief organizations manage disaster events, track available supplies, and ensure timely delivery to affected areas.

The system provides a centralized platform to:
- Register and manage **disaster-affected families**
- Track and restock **relief inventory** in real time
- Generate **operational reports** for better decision-making
- Restrict access to **authorized personnel** only

Built with **Java Swing** for a responsive desktop UI and **MySQL** for reliable persistent data storage, **ReliefTrack** is designed for fast deployment in resource-constrained environments where simplicity and reliability matter most.

---

## ✨ Key Features

| Feature | Description |
|---|---|
| 🔐 **User Authentication** | Secure login interface restricting access to authorized users only |
| 👨‍👩‍👧 **Family Registration** | Register, view, and manage disaster-affected households |
| 📦 **Inventory Management** | Track all available relief supplies with real-time quantity monitoring |
| 🔄 **Restocking Module** | Add new stock or replenish existing supplies with ease |
| 📊 **Inventory Dashboard** | Monitor stock levels and identify shortages at a glance |
| 📋 **Report Generation** | Generate data-driven reports for families and inventory records |
| 🗄️ **MySQL Integration** | Reliable relational database backend for persistent data storage |
| 🖥️ **Desktop Deployment** | Minimal setup — runs on any machine with Java installed |

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────┐
│          PRESENTATION LAYER                  │
│       Java Swing UI Components               │
│  LoginUI · MainUI · InventoryUI · ReportUI  │
└──────────────────┬──────────────────────────┘
                   │
┌──────────────────▼──────────────────────────┐
│         BUSINESS LOGIC LAYER                 │
│    Inventory & Operational Management        │
│            InventoryManager.java             │
└──────────────────┬──────────────────────────┘
                   │
┌──────────────────▼──────────────────────────┐
│          DATA ACCESS LAYER                   │
│       JDBC-Based DB Connectivity             │
│              DBConnection.java               │
└──────────────────┬──────────────────────────┘
                   │
┌──────────────────▼──────────────────────────┐
│           DATABASE LAYER                     │
│        MySQL Relational Database             │
│            disaster_relief DB                │
└─────────────────────────────────────────────┘
```

---

## 🛠️ Technology Stack

| Component | Technology |
|---|---|
| **Programming Language** | Java 8+ |
| **GUI Framework** | Java Swing |
| **Database** | MySQL |
| **DB Connectivity** | JDBC |
| **MySQL Driver** | mysql-connector 8.033-java.jar |
| **Table Rendering** | rs2xml.jar |

---

## 📁 Project Structure

```
ReliefTrack/
│
├── 📂 database/
│   └── sqlcode.sql                      # Full DB schema & seed data
│
├── 📂 disasterrelief/
│   ├── DBConnection.java                # Manages JDBC connection & credentials
│   ├── Family.java                      # Family data model
│   ├── InventoryItem.java               # Relief item data model
│   ├── InventoryManager.java            # Core inventory business logic
│   ├── InventoryUI.java                 # Inventory overview panel
│   ├── LoginUI.java                     # Authentication screen (entry point)
│   ├── MainUI.java                      # Main dashboard & navigation
│   ├── manageFamiliesUI.java            # Family management panel
│   ├── RegisterFamilyUI.java            # New family registration form
│   ├── report.java                      # Report generation
│   ├── RestockUI.java                   # Supply restocking panel
│   ├── rs2xml.jar                       # ResultSet-to-JTable utility (bundled)
│   └── ViewInventoryUI.java             # Inventory detail view
│
├── 📂 icon/
│   └── login.png                        # Application icon assets
│
└── README.md
```

---

## ✅ Prerequisites

Before running the project, make sure the following are installed and ready:

| Requirement | Details |
|---|---|
| ☕ **Java JDK 8+** | [Download here](https://www.oracle.com/java/technologies/downloads/) |
| 🐬 **MySQL Server** | [Download here](https://dev.mysql.com/downloads/mysql/) |
| 🖥️ **CMD / Terminal** | Built-in on Windows, Linux, and macOS |
| 💡 **Java IDE** *(optional)* | IntelliJ IDEA / Eclipse / NetBeans |
| 📦 **Required JARs** | `mysql-connector-8.033-java.jar` *(in project root)*, `rs2xml.jar` *(inside `disasterrelief/`)* |

> ⚠️ **Important:** If any required JAR file or MySQL connector is missing, **ReliefTrack** will **not** run. Ensure both JARs are present before compiling.

---

## ⚙️ Installation & Setup

### Step 1 — Clone the Repository

```bash
git clone https://github.com/deepaklal-io/relieftrack.git
cd relieftrack
```

### Step 2 — Set Up the MySQL Database

1. Open **MySQL Workbench** or the **MySQL Command Line**.
2. Open the provided SQL file: `database/sqlcode.sql`
3. Execute all SQL statements to create the database and tables:

```sql
-- Run this in MySQL Workbench or CLI
SOURCE path/to/database/sqlcode.sql;
```

Or via terminal:

```bash
mysql -u root -p < database/sqlcode.sql
```

4. Open `disasterrelief/DBConnection.java` and update the credentials:

```java
private static final String URL      = "jdbc:mysql://localhost:3306/disasterrelief";
private static final String USERNAME = "your_mysql_username";
private static final String PASSWORD = "your_mysql_password";
```

> ⚠️ **Note:** If the database credentials are not set correctly, the login functionality will **not** work properly.

---

## ▶️ Running the Application

You can run **ReliefTrack** in two ways — via **Command Prompt / Terminal** or using an **IDE**.

---

### Option A — Run Using Command Prompt (CMD)

#### 1️⃣ Open Command Prompt and navigate to the project folder

```bash
cd C:\Users\YourUsername\Desktop\ReliefTrack
```

#### 2️⃣ Compile all Java files in the `disasterrelief` package

```bash
javac disasterrelief/*.java
```

This compiles all Java source files inside the package directory.

#### 3️⃣ Run the application

Make sure the class you run contains the `public static void main(String[] args)` method.

**To launch the Login screen:**
```bash
java disasterrelief.LoginUI
```

**Or to launch the Main dashboard directly:**
```bash
java disasterrelief.MainUI
```

> 💡 **Tip (Windows):** If you encounter classpath errors with JARs, use:
> ```bash
> javac -cp "disasterrelief/rs2xml.jar;disasterrelief/mysql-connector-8.033-java.jar" disasterrelief/*.java
> java -cp ".;disasterrelief/rs2xml.jar;disasterrelief/mysql-connector-8.033-java.jar" disasterrelief.LoginUI
> ```
> On **Linux/macOS**, replace `;` with `:` in the classpath.

---

### Option B — Run Using an IDE

1. Open **IntelliJ IDEA**, **Eclipse**, or **NetBeans**.
2. Import the project as an **existing Java project**.
3. Add the required JARs to the build path:
   - `disasterrelief/rs2xml.jar`
   - `mysql-connector-8.033-java.jar`
4. Ensure the **MySQL Server is running**.
5. Locate `LoginUI.java` or `MainUI.java`.
6. Right-click the file → select **Run**.

---

## 🖥️ Application Modules

### 🔐 Login Module
Entry point of **ReliefTrack**. Handles secure authentication and restricts access to authorized personnel only.

### 👨‍👩‍👧 Family Management
Register and manage disaster-affected households. Captures key details like the head of family, address, contact information, and household size.

### 📦 Inventory Management
Real-time tracking of all available relief resources. View quantities and quickly identify what's running low.

### 🔄 Restocking Module
Allows administrators to add new inventory items or top up quantities of existing supplies.

### 📊 Inventory Dashboard
An at-a-glance monitoring panel for current stock levels across all relief categories.

### 📋 Report Generation
Generates structured reports for family records and inventory data — essential for coordination between field teams and headquarters.

---

## 🗃️ Data Models

### `Family`
| Field | Type | Description |
|---|---|---|
| `familyId` | INT | Unique household identifier |
| `headOfFamily` | VARCHAR | Name of the registered head |
| `address` | VARCHAR | Current location or address |
| `contactInfo` | VARCHAR | Phone or contact details |
| `householdSize` | INT | Total number of family members |

### `InventoryItem`
| Field | Type | Description |
|---|---|---|
| `itemId` | INT | Unique item identifier |
| `itemName` | VARCHAR | Name of the relief item |
| `description` | VARCHAR | Additional item details |
| `quantity` | INT | Current stock count |

---

## 📝 Important Notes

- ✅ Ensure the **MySQL server is running** before launching **ReliefTrack**.
- ✅ Keep `rs2xml.jar` inside the `disasterrelief/` folder — it is required for table display.
- ✅ Do **not** delete `.class` files after compilation unless you plan to recompile.
- ✅ Always verify your database credentials in `DBConnection.java` before running.
- ✅ For production use, store DB credentials in environment variables — never hardcode them.

---

## 🔒 Security Considerations

- **Never commit credentials** to version control — use environment variables or a `.env` config file excluded via `.gitignore`.
- **Use parameterized queries** (`PreparedStatement`) in all DB interactions to prevent SQL injection.
- **Restrict MySQL user permissions** — grant only `SELECT`, `INSERT`, `UPDATE`, `DELETE` on the `disaster_relief` database.

---

## 🐛 Troubleshooting

| Problem | Likely Cause | Solution |
|---|---|---|
| `Connection refused` | MySQL server not running | Start the MySQL service |
| `Access denied for user` | Wrong DB credentials | Update `DBConnection.java` |
| `ClassNotFoundException` for driver | JAR missing from classpath | Add `mysql-connector.jar` to `-cp` |
| `Table doesn't exist` | Schema not imported | Re-run `sqlcode.sql` |
| Blank JTable on load | `rs2xml.jar` missing | Add it to the classpath |
| Compilation errors | Wrong package path | Run `javac` from the project root |

---

## 🚀 Future Improvements

- [ ] 🌐 Web-based interface (Spring Boot + React)
- [ ] ☁️ Cloud database integration (AWS RDS / Firebase)
- [ ] 🔑 Role-based access control (Admin, Operator, Viewer)
- [ ] 📝 Audit logging for all system actions
- [ ] 📈 Advanced analytics and reporting dashboard
- [ ] 📱 Mobile companion app for field workers
- [ ] 🌍 Multi-language / localization support
- [ ] 🔔 Low-stock alerts and notifications

---

## 🤝 Contributing

Contributions are welcome! Here's how to get involved:

1. **Fork** the repository
2. **Create** a feature branch
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Commit** your changes with a clear message
   ```bash
   git commit -m "feat: add your feature description"
   ```
4. **Push** to your fork
   ```bash
   git push origin feature/your-feature-name
   ```
5. **Open a Pull Request** — describe what you changed and why

---

## 👥 Authors & Contributors

| Name | GitHub |
|---|---|
| **Shahzaib Mahar** | [@smaharx](https://github.com/smaharx) |
| **Najaf** | [@najafalinajaf449-hue](https://github.com/najafalinajaf449-hue) |
| **Deepak** | [@deepaklal-io](https://github.com/deepaklal-io) |

---

## ✅ Conclusion

**ReliefTrack** provides an efficient and reliable solution for managing disaster relief supply distribution using **Java** and **MySQL** through **JDBC connectivity**. Whether deployed by a field team or a coordination center, it delivers the structure and reliability needed when it matters most.

---

<div align="center">

Made with ❤️ to support disaster relief operations

⭐ If this project helped you, please consider giving it a star on GitHub!

</div>
