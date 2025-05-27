# 🐆 Wildlife Conservation Monitoring Assignment

### 1️⃣ PostgreSQL কি?

PostgreSQL হলো একটি আধুনিক, ওপেন সোর্স রিলেশনাল ডেটাবেস ম্যানেজমেন্ট সিস্টেম (RDBMS)। এটি ACID নীতিমালার প্রতি শ্রদ্ধাশীল এবং জটিল ডেটা স্ট্রাকচার, ট্রানজ্যাকশন হ্যান্ডলিং ও এক্সটেনশনের জন্য বিখ্যাত।

**উদাহরণ:**

```sql
CREATE TABLE students (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    age INT
);
```

### 2️⃣ PostgreSQL-এ ডেটাবেস স্কিমার উদ্দেশ্য

স্কিমা হলো একটি লজিক্যাল কাঠামো যা ডেটাবেসের বিভিন্ন অবজেক্ট সংগঠিতভাবে রাখে। এটি নামের সংঘর্ষ এড়াতে সহায়তা করে।

**উদাহরণ:**

```sql
CREATE SCHEMA hr;
CREATE TABLE hr.employees (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(50)
);
```

### 3️⃣ Primary Key এবং Foreign Key

- **Primary Key**: টেবিলের প্রতিটি রেকর্ডকে ইউনিকভাবে চিহ্নিত করে
- **Foreign Key**: এক টেবিলের কলাম যা অন্য টেবিলের Primary Key এর সাথে সম্পর্ক স্থাপন করে

**উদাহরণ:**

```sql
CREATE TABLE departments (
    dept_id SERIAL PRIMARY KEY,
    dept_name VARCHAR(100)
);

CREATE TABLE employees (
    emp_id SERIAL PRIMARY KEY,
    emp_name VARCHAR(100),
    dept_id INT,
    FOREIGN KEY (dept_id) REFERENCES departments(dept_id)
);
```

### 4️⃣ VARCHAR এবং CHAR এর পার্থক্য

- **VARCHAR(n)**: পরিবর্তনশীল দৈর্ঘ্যের টেক্সট
- **CHAR(n)**: নির্দিষ্ট দৈর্ঘ্যের টেক্সট

**উদাহরণ:**

```sql
CREATE TABLE var_table (
    name VARCHAR(10)  -- "Ali" স্টোর করবে
);

CREATE TABLE char_table (
    name CHAR(10)     -- "Ali       " স্টোর করবে
);
```

### 5️⃣ SELECT স্টেটমেন্টে WHERE ক্লজ

WHERE ক্লজ SQL কোয়েরিতে শর্ত নির্ধারণ করতে ব্যবহৃত হয়। এটি নির্দিষ্ট রেকর্ড ফিল্টার করতে সাহায্য করে।

**উদাহরণ:**

```sql
SELECT * FROM students
WHERE age > 18;
```
