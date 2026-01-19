#  BuyBuddy: Smart Grocery Recommendation System

**BuyBuddy** is an intelligent, full-stack grocery recommendation system for e-commerce platforms. It delivers **real-time, context-aware suggestions** using advanced market basket analysis, FP-Growth algorithm, and seasonal/time-of-day enhancements.

---

##  Features

*  **User Authentication** — Secure registration, login, and profile management
*  **Product Management** — Add, update, and organize grocery catalog
* 🛒 **Transaction Logging** — Track and analyze real-time purchase behavior
*  **Smart Recommendations**:

  * Context-aware (based on time of day)
  * Seasonal product boosting (based on monthly trends)
  * Real-world grocery transaction insights
*  **RESTful API Access** — Fully documented and ready-to-use endpoints
*  **Interactive Dashboard** — User-friendly UI for monitoring & control
*  **One-Click Setup** — Automatic installation, database config & demo run

---

##  Use Cases

* Plug-and-play recommendation engine for grocery stores
* B2B SaaS base for personalized grocery upselling
* Research-backed model to demonstrate FP-Growth in real scenarios

---

##  Tech Stack

| Layer     | Technology                              |
| --------- | --------------------------------------- |
| Backend   | Python 3.11, Flask, SQLAlchemy, JWT     |
| Database  | PostgreSQL                              |
| Algorithm | Optimized FP-Growth with pandas + numpy |
| Frontend  | HTML, Bootstrap 5, Jinja Templates      |
| API Docs  | Flasgger (OpenAPI / Swagger)            |

---

##  Installation Guide

###  Prerequisites

* Python 3.9+
* PostgreSQL (running)
* `pip` (Python package installer)

---

###  Option 1: Automated Setup (Recommended)

1. **Clone the repository**

   ```bash
   git clone https://github.com/snehaagrawal14/BuyBuddy.git
   cd BuyBuddy
   ```

2. **Run the setup script**

   ```bash
   python setup.py
   ```

   This script will:

   * Install dependencies
   * Prompt for PostgreSQL credentials
   * Create database and tables
   * Configure `.env` file
   * Load real grocery dataset
   * Start the application

3. **Access the app** Visit: `http://localhost:5000`

   * Demo login:

     * `username: admin`
     * `password: adminpassword`

---

###  Option 2: Manual Setup

1. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

2. **Configure PostgreSQL**

   ```sql
   CREATE DATABASE buybuddy OWNER your_username;
   GRANT ALL PRIVILEGES ON DATABASE buybuddy TO your_username;
   ```

3. **Create `.env` file**

   ```
   DATABASE_URL=postgresql://your_username:your_password@localhost:5432/buybuddy
   SESSION_SECRET=your-session-secret
   ```

4. **Initialize the DB**

   ```bash
   python -c "from app import app; print('Database initialized')"
   ```

5. **Run the app**

   ```bash
   python -m flask run
   ```

   Or in production:

   ```bash
   gunicorn --bind 0.0.0.0:5000 main:app
   ```

---

##  Default Credentials

* **Username:** `admin`
* **Password:** `adminpassword`

---

##  API Documentation

Access interactive Swagger documentation:

```
http://localhost:5000/docs/
```

---

##  Recommendation Engine

###  Time-of-Day Context

* **Morning (5am–11am)**: Coffee, milk, breakfast
* **Midday (11am–3pm)**: Lunch ingredients, quick meals
* **Evening (3pm–9pm)**: Dinner items, daily essentials
* **Late Night (9pm–5am)**: Snacks, beverages

###  Seasonal Boosting

| Month       | Example Boosted Products                     |
| ----------- | -------------------------------------------- |
| January     | Health foods, vitamins, detox kits           |
| February    | Chocolates, roses, dinner ingredients        |
| March/April | Spring cleaning, gardening, Easter items     |
| May         | Grill items, juices, outdoor picnic supplies |
| June–Aug    | Summer drinks, ice creams, coolers           |
| September   | School snacks, lunch boxes                   |
| October     | Halloween candy, pumpkin spice items         |
| November    | Thanksgiving foods, gravy, cranberry sauce   |
| December    | Holiday sweets, baking supplies, dry fruits  |

---

##  Dataset Insights

* **Market Basket Dataset** — 9,800+ grouped grocery transactions
  [`groceries.csv`](https://github.com/stedy/Machine-Learning-with-R-datasets) from stedy/Machine-Learning-with-R-datasets

* **Grocery Transactions Dataset** — 38,000+ real sales with member IDs, dates
  [`Groceries_dataset.csv`](https://github.com/amankharwal/Website-data) from amankharwal/Website-data

* **Preprocessed & Cleaned** — Duplicate removal, category normalization

* **FP-Growth Optimized** — Weighted rules with support & confidence thresholds

---

##  Folder Structure

```bash
BuyBuddy/
│
├── app/                 # Flask application
│   ├── routes/          # API + web routes
│   ├── models/          # SQLAlchemy models
│   └── templates/       # Jinja2 HTML templates
│
├── utils/               # FP-Growth logic, dataset processing
├── data/                # Sample + real grocery datasets
├── static/              # Bootstrap, JS, icons, screenshots
├── setup.py             # One-click installer
├── .env                 # Environment variables
├── requirements.txt     # Python packages
└── README.md            # Project documentation
```

---

## 🢞 Troubleshooting

### 🔌 Database Not Connecting?

* Ensure PostgreSQL service is running
* Confirm `.env` file is correctly configured
* Run `psql -l` to verify database exists

###  App Not Starting?

* Double-check `pip` dependencies
* Ensure port `5000` is free
* Read logs printed in console for clues

---

##  Contributing

Contributions are welcome! If you’d like to improve the engine, optimize rules, or extend the dashboard — feel free to fork the project and submit a PR.

---

##  License

MIT License © 2025

---

##  Acknowledgments

* [mlxtend](http://rasbt.github.io/mlxtend/) for FP-Growth support
* Dataset sources:

  * [`groceries.csv`](https://github.com/stedy/Machine-Learning-with-R-datasets) from stedy/Machine-Learning-with-R-datasets
  * [`Groceries_dataset.csv`](https://github.com/amankharwal/Website-data) from amankharwal/Website-data
* Inspired by real-world e-commerce recommendation engines
