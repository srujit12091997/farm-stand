# Express Farm Stand with MongoDB & Mongoose

A full-stack web application built using Express.js, MongoDB, and Mongoose, demonstrating CRUD operations and database integration for managing farm produce inventory.

##  Author

**Srujit Varasala**
- GitHub: [@srujit12091997](https://github.com/srujit12091997)
- LinkedIn: [srujitvarasala](https://www.linkedin.com/in/srujitvarasala/)

##  Project Overview

This project showcases the integration of:
- **MongoDB** as the NoSQL database
- **Mongoose** for elegant MongoDB object modeling
- **Express.js** for server-side logic
- **EJS** for dynamic view rendering

##  Tech Stack

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web application framework
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB object modeling tool

### Frontend
- **EJS** - Embedded JavaScript templating
- **HTML/CSS** - Basic styling and structure

### Development Tools
- **Nodemon** - Auto-reload during development
- **Method-Override** - HTTP method handling

##  Prerequisites

- MongoDB (v4.4 or later)
- Node.js (v14 or later)
- npm (Node Package Manager)

##  MongoDB Setup & Configuration

1. **Database Connection**
   ```javascript
   mongoose.connect('mongodb://localhost:27017/farmStand', { 
       useNewUrlParser: true, 
       useUnifiedTopology: true 
   })
   ```

2. **Mongoose Schema**
   ```javascript
   const productSchema = new mongoose.Schema({
       name: {
           type: String,
           required: true
       },
       price: {
           type: Number,
           required: true,
           min: 0
       },
       category: {
           type: String,
           lowercase: true,
           enum: ['fruit', 'vegetable', 'dairy']
       }
   });
   ```

##  Installation & Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/srujit12091997/farm-stand.git
   cd farm-stand
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start MongoDB service**
   ```bash
   # For Windows
   net start MongoDB
   
   # For macOS/Linux
   sudo service mongod start
   ```

4. **Seed the database (optional)**
   ```bash
   node seeds.js
   ```

5. **Run the application**
   ```bash
   npm start
   ```

## Project Structure

```
farm-stand/
├── models/
│   └── product.js        # Mongoose schema and model
├── views/
│   └── products/
│       ├── index.ejs     # Products listing
│       ├── new.ejs       # Create form
│       ├── edit.ejs      # Edit form
│       └── show.ejs      # Product details
├── seeds.js              # Database seeder
├── index.js              # Main application file
└── package.json
```

##  Mongoose Operations Demonstrated

```javascript
// Create
const newProduct = new Product(req.body);
await newProduct.save();

// Read
const products = await Product.find({});
const product = await Product.findById(id);

// Update
const updatedProduct = await Product.findByIdAndUpdate(id, req.body, 
    { runValidators: true, new: true });

// Delete
await Product.findByIdAndDelete(id);

// Query with filters
const products = await Product.find({ category });
```

##  RESTful Routes

| Method | Path | Mongoose Operation | Purpose |
|--------|------|-------------------|----------|
| GET | /products | Product.find() | List products |
| POST | /products | new Product(), save() | Create product |
| GET | /products/:id | Product.findById() | Show product |
| PUT | /products/:id | Product.findByIdAndUpdate() | Update product |
| DELETE | /products/:id | Product.findByIdAndDelete() | Delete product |

##  Features

- **MongoDB Integration**
  - Mongoose schema validation
  - Efficient CRUD operations
  - Category-based filtering

- **Data Management**
  - Create and update products
  - Validate input data
  - Filter products by category

##  Learning Implementation

- MongoDB database design
- Mongoose schema modeling
- Express route handling
- Async/await operations
- Error handling
- Form validation

##  Database Operations

The project implements various Mongoose methods:
- `find()`
- `findById()`
- `findByIdAndUpdate()`
- `findByIdAndDelete()`
- Custom queries with filters



⭐️ Developed by [Srujit Varasala](https://github.com/srujit12091997) ⭐️
