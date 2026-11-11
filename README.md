# Inventory and Supply Chain Dashboard

An interactive dashboard built with **Python, Streamlit and SQL** that tracks inventory, suppliers, stock movement and reorders. Data is stored in a cloud-hosted MySQL-compatible database (TiDB Cloud), and the app is deployed on Streamlit Community Cloud.

**Live app:** https://inventorymanagement-systempythonui-4fzhqktcw9tpkl264vursn.streamlit.app


## What the project does

The dashboard has two sections, chosen from the sidebar:

- **Basic Information:** headline inventory metrics calculated live from the database
  - Total suppliers
  - Total products
  - Total product categories
  - Total sale value in the last 3 months
  - Total restock value in the last 3 months
  - Products below reorder level with no pending reorder
- **Operational Tasks:** day-to-day inventory operations on top of the same database

## Tech stack

| Area | Tools |
|------|-------|
| Language | Python |
| Web UI | Streamlit |
| Database | MySQL-compatible (TiDB Cloud) |
| Data handling | Pandas, mysql-connector-python |
| Hosting | Streamlit Community Cloud |

## Database design

The database `inventory_db` has 5 related tables:

- `products`: product details, category and price
- `suppliers`: supplier information
- `stock_entries`: every stock change (sales, restocks) with date and quantity
- `shipments`: incoming shipment records
- `reorders`: reorder requests and their status

## SQL skills used

The queries in the `sql/` folder use:

- Joins across multiple tables
- Aggregations (`COUNT`, `SUM`, `ROUND`, `COUNT(DISTINCT ...)`)
- Subqueries
- Date functions such as `DATE_SUB` for rolling 3-month windows
- Filtering on change type (sale vs restock)

## Project structure

```
inventory_management-_system_python_ui/
├── app.py              # Streamlit user interface
├── db_functions.py     # Database connection and query functions
├── requirements.txt    # Python dependencies
├── data/               # CSV files used to load the database
├── sql/                # SQL queries used for analysis
└── README.md
```

## Run it locally

1. Clone the repository:
   ```
   git clone https://github.com/ayushibais/inventory_management-_system_python_ui.git
   cd inventory_management-_system_python_ui
   ```
2. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
3. Create a file `.streamlit/secrets.toml` with your own database details:
   ```
   [mysql]
   host = "your-host"
   port = 3306
   user = "your-user"
   password = "your-password"
   database = "inventory_db"
   ```
4. Load the CSV files from `data/` into your database as tables with the names listed above.
5. Start the app:
   ```
   streamlit run app.py
   ```

## Security note

Database credentials are not stored in the code. They are read from Streamlit Secrets (`st.secrets`) so they never appear in the public repository.

## Key learnings

- Designing a relational database and loading data from CSV files
- Writing SQL for business questions such as sales value, restock value and reorder alerts
- Connecting a Python app to a cloud database securely
- Deploying a data application end to end

## Author

**[Ayushi Bais]**
[https://www.linkedin.com/in/ayushi-bais-a5620b212?utm_source=share_via&utm_content=profile&utm_medium=member_ios] | [ayushib1219@gmail.com]# Inventory_Management-_system_Python_UI


<img width="898" height="393" alt="image" src="https://github.com/user-attachments/assets/1949d6f8-98f8-4b51-a55e-04bff74da064" />

<img width="952" height="462" alt="image" src="https://github.com/user-attachments/assets/5ed57f0f-bfde-4838-a2ca-0a196771a374" />
<img width="635" height="236" alt="image" src="https://github.com/user-attachments/assets/83814021-b266-4119-8098-9fc0a8b0675f" />

