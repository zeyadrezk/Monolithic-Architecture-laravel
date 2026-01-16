# Monolithic Architecture - Laravel Learning Project

> **Part 1 of Laravel Architecture Series** | Your journey to mastering Laravel architecture starts here!

[![Laravel](https://img.shields.io/badge/Laravel-12-red.svg)](https://laravel.com)
[![PHP](https://img.shields.io/badge/PHP-8.2+-blue.svg)](https://php.net)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## Table of Contents

- [What is This Project?](#what-is-this-project)
- [What is Monolithic Architecture?](#what-is-monolithic-architecture)
- [Project Plan](#project-plan)
- [What You'll Learn](#what-youll-learn)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Features Overview](#features-overview)
- [Development Roadmap](#development-roadmap)
- [Understanding the Code](#understanding-the-code)
- [Best Practices](#best-practices)
- [Testing](#testing)
- [Deployment](#deployment)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [Resources](#resources)

---

## What is This Project?

This is a **beginner-friendly** Laravel application demonstrating the **Monolithic Architecture** pattern. It's designed as an educational resource to help you understand:

- How modern web applications are structured
- What monolithic architecture means in practice
- Laravel's best practices and conventions
- Clean code organization
- Testing fundamentals
- When to use (and when not to use) monolithic architecture

**Perfect for:**
- Laravel beginners
- Developers learning software architecture
- Students building their first real-world projects
- Anyone wanting to understand monolithic patterns

---

## What is Monolithic Architecture?

### Simple Definition

A **monolithic application** is like a **self-contained house** where everything you need is under one roof:
- All features in one codebase
- Single database
- Components communicate directly
- Deploy everything together

### Real-World Analogy

Imagine a **traditional restaurant**:
- Kitchen (business logic)
- Dining area (user interface)
- Storage room (database)
- Cash register (payment processing)

Everything operates in one building, staff can walk directly between areas, and you manage it all as one business.

### Key Characteristics

```
┌─────────────────────────────────────┐
│     Monolithic Application          │
├─────────────────────────────────────┤
│  User Interface (Views/API)         │
├─────────────────────────────────────┤
│  Business Logic (Controllers/       │
│  Services/Models)                   │
├─────────────────────────────────────┤
│  Data Layer (Database)              │
└─────────────────────────────────────┘
     All in ONE deployment
```

**Characteristics:**
- ✅ Single codebase
- ✅ Shared database
- ✅ Direct function calls
- ✅ One deployment unit
- ✅ Simple to understand

---

## Project Plan

This project will build a **Task Management System** - a simple but complete application demonstrating monolithic architecture.

### Application Features

#### 1. User Authentication
- User registration
- Login/Logout
- Password reset
- Email verification
- Remember me functionality

#### 2. Task Management (CRUD)
- Create tasks
- View all tasks (list + details)
- Update tasks
- Delete tasks
- Mark tasks as complete/incomplete

#### 3. Categories
- Create categories
- Assign tasks to categories
- Filter tasks by category
- Category colors/icons

#### 4. User Dashboard
- View user statistics
- Recent tasks
- Completion rate
- Activity timeline

#### 5. Search & Filtering
- Search tasks by title/description
- Filter by status (pending/completed)
- Filter by category
- Sort by date, priority, etc.

### Technical Features to Demonstrate

#### Core Laravel Concepts
- **Routing** - Web routes, route parameters, route model binding
- **Controllers** - Resource controllers, single action controllers
- **Models** - Eloquent ORM, relationships, scopes
- **Migrations** - Database version control
- **Validation** - Form request validation
- **Blade Templates** - Views, layouts, components
- **Middleware** - Authentication, authorization

#### Architecture Patterns
- **MVC Pattern** - Model-View-Controller separation
- **Service Layer** - Business logic organization
- **Repository Pattern** (optional) - Data access abstraction
- **Request/Response Pattern** - HTTP handling
- **Observer Pattern** - Model events

#### Best Practices
- **Clean Code** - Readable, maintainable code
- **SOLID Principles** - Basic implementation
- **DRY** - Don't Repeat Yourself
- **Testing** - Unit and Feature tests
- **Documentation** - Well-commented code

---

## What You'll Learn

### Beginner Level (Week 1)

**Laravel Fundamentals:**
- ✅ How to set up a Laravel project
- ✅ Understanding Laravel's folder structure
- ✅ Creating routes and controllers
- ✅ Working with Blade templates
- ✅ Database migrations and seeders

**Basic CRUD:**
- ✅ Create: Adding new tasks
- ✅ Read: Displaying tasks
- ✅ Update: Editing tasks
- ✅ Delete: Removing tasks

### Intermediate Level (Week 2)

**Relationships:**
- ✅ One-to-Many (User has many Tasks)
- ✅ Many-to-One (Task belongs to Category)
- ✅ Eloquent relationships in practice

**Form Validation:**
- ✅ Request validation
- ✅ Custom validation rules
- ✅ Error handling and display

**Authentication:**
- ✅ Laravel Breeze setup
- ✅ Protected routes
- ✅ User authorization

### Advanced Level (Week 3-4)

**Clean Architecture:**
- ✅ Service classes for business logic
- ✅ Separation of concerns
- ✅ Dependency injection
- ✅ Interface segregation

**Testing:**
- ✅ Feature tests with Pest
- ✅ Database testing
- ✅ Test-driven development basics
- ✅ Mocking and factories

**Production Readiness:**
- ✅ Error handling
- ✅ Logging
- ✅ Security best practices
- ✅ Performance optimization

---

## Prerequisites

### Required Knowledge

**You should know:**
- PHP basics (variables, functions, classes, arrays)
- HTML & CSS fundamentals
- Basic SQL (SELECT, INSERT, UPDATE, DELETE)
- Command line basics
- Git basics

**Nice to have:**
- Object-oriented programming concepts
- MVC pattern understanding
- HTTP request/response cycle

### Required Software

| Software | Version | Purpose |
|----------|---------|---------|
| PHP | 8.2+ | Server-side language |
| Composer | Latest | PHP dependency manager |
| Node.js | 18+ | Frontend asset compilation |
| npm | Latest | JavaScript package manager |
| MySQL/PostgreSQL/SQLite | Any | Database (SQLite recommended for learning) |
| Git | Latest | Version control |

### Optional Tools

- **Laravel Herd/Valet** - Local development environment
- **TablePlus/phpMyAdmin** - Database GUI
- **VS Code** - Code editor with PHP extensions
- **Postman/Insomnia** - API testing

---

## Installation

### Step 1: Clone the Repository

```bash
cd /Users/zeyad/Zeyad/Work/laravel-lab
git clone <your-repo-url> Monolithic-Architecture-laravel
cd Monolithic-Architecture-laravel
```

### Step 2: Install PHP Dependencies

```bash
composer install
```

This installs all Laravel packages and dependencies.

### Step 3: Install JavaScript Dependencies

```bash
npm install
```

This installs frontend build tools (Vite, Tailwind CSS, etc.).

### Step 4: Environment Setup

```bash
# Copy environment file
cp .env.example .env

# Generate application key (IMPORTANT!)
php artisan key:generate
```

### Step 5: Configure Database

**Option A: SQLite (Recommended for Beginners)**

```bash
# Create SQLite database file
touch database/database.sqlite
```

Edit `.env`:
```env
DB_CONNECTION=sqlite
# Comment out or remove these lines:
# DB_HOST=127.0.0.1
# DB_PORT=3306
# DB_DATABASE=laravel
```

**Option B: MySQL**

Edit `.env`:
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=task_manager
DB_USERNAME=your_username
DB_PASSWORD=your_password
```

Create the database:
```bash
mysql -u root -p
CREATE DATABASE task_manager;
exit;
```

### Step 6: Run Migrations

```bash
php artisan migrate
```

This creates all database tables.

### Step 7: Seed Database (Optional)

```bash
php artisan db:seed
```

This adds sample data for testing.

### Step 8: Build Frontend Assets

```bash
npm run dev
```

### Step 9: Start Development Server

**Option A: Using Composer Script**
```bash
composer dev
```

This runs the server, queue, logs, and Vite concurrently.

**Option B: Manual**
```bash
# Terminal 1 - Laravel server
php artisan serve

# Terminal 2 - Frontend assets
npm run dev
```

### Step 10: Visit Application

Open your browser:
```
http://localhost:8000
```

You should see the application homepage!

---

## Project Structure

```
Monolithic-Architecture-laravel/
│
├── app/
│   ├── Http/
│   │   ├── Controllers/          # Handle HTTP requests
│   │   │   ├── TaskController.php
│   │   │   ├── CategoryController.php
│   │   │   └── DashboardController.php
│   │   ├── Middleware/           # Request filtering
│   │   └── Requests/             # Form validation
│   │       ├── StoreTaskRequest.php
│   │       └── UpdateTaskRequest.php
│   │
│   ├── Models/                   # Database models
│   │   ├── Task.php
│   │   ├── Category.php
│   │   └── User.php
│   │
│   ├── Services/                 # Business logic
│   │   ├── TaskService.php
│   │   └── DashboardService.php
│   │
│   └── Providers/                # Service providers
│
├── database/
│   ├── migrations/               # Database structure
│   │   ├── 2024_01_01_create_tasks_table.php
│   │   └── 2024_01_02_create_categories_table.php
│   ├── seeders/                  # Sample data
│   │   ├── TaskSeeder.php
│   │   └── CategorySeeder.php
│   └── factories/                # Model factories
│
├── resources/
│   ├── views/                    # Blade templates
│   │   ├── layouts/
│   │   │   └── app.blade.php
│   │   ├── tasks/
│   │   │   ├── index.blade.php
│   │   │   ├── create.blade.php
│   │   │   ├── edit.blade.php
│   │   │   └── show.blade.php
│   │   ├── categories/
│   │   └── dashboard/
│   └── css/                      # Stylesheets
│
├── routes/
│   ├── web.php                   # Web routes
│   └── api.php                   # API routes (future)
│
├── tests/
│   ├── Feature/                  # Integration tests
│   │   ├── TaskTest.php
│   │   └── CategoryTest.php
│   └── Unit/                     # Unit tests
│
├── public/                       # Publicly accessible files
│   └── index.php                 # Entry point
│
├── config/                       # Configuration files
├── storage/                      # Logs, cache, uploads
└── vendor/                       # Composer dependencies
```

### Folder Purpose Explained

| Folder | Purpose | You'll Work Here |
|--------|---------|------------------|
| `app/Http/Controllers` | Handle HTTP requests | ⭐⭐⭐ Often |
| `app/Models` | Database models | ⭐⭐⭐ Often |
| `app/Services` | Business logic | ⭐⭐ Sometimes |
| `database/migrations` | Database structure | ⭐⭐⭐ Often |
| `resources/views` | HTML templates | ⭐⭐⭐ Often |
| `routes/web.php` | Define URLs | ⭐⭐⭐ Often |
| `tests/` | Automated tests | ⭐⭐ Sometimes |

---

## Features Overview

### 1. Task Management (Core Feature)

**What it does:**
Users can create, view, update, and delete tasks.

**Files involved:**
- `app/Http/Controllers/TaskController.php` - Handles requests
- `app/Models/Task.php` - Task data model
- `resources/views/tasks/*` - Task views
- `database/migrations/*_create_tasks_table.php` - Database structure

**Key learning points:**
- CRUD operations
- Eloquent ORM
- Route model binding
- Form validation

### 2. Categories

**What it does:**
Organize tasks into categories (Work, Personal, Shopping, etc.).

**Files involved:**
- `app/Http/Controllers/CategoryController.php`
- `app/Models/Category.php`
- `resources/views/categories/*`

**Key learning points:**
- One-to-Many relationships
- Cascade deletes
- Foreign keys

### 3. User Dashboard

**What it does:**
Show user statistics and recent activity.

**Files involved:**
- `app/Http/Controllers/DashboardController.php`
- `app/Services/DashboardService.php`
- `resources/views/dashboard.blade.php`

**Key learning points:**
- Data aggregation
- Service layer pattern
- Query optimization

### 4. Authentication

**What it does:**
User registration, login, and access control.

**Files involved:**
- Laravel Breeze scaffolding
- `routes/auth.php`
- `resources/views/auth/*`

**Key learning points:**
- Authentication middleware
- Authorization gates
- Session management

---

## Development Roadmap

### Phase 1: Foundation (Week 1)

- [x] Fresh Laravel 12 installation
- [x] Pest testing framework setup
- [ ] Install Laravel Breeze for authentication
- [ ] Create database schema (migrations)
- [ ] Set up basic routing
- [ ] Create base layout and design

**Learning Focus:** Laravel basics, project setup

### Phase 2: Core Features (Week 2)

- [ ] Implement Task CRUD
  - [ ] Task model and migration
  - [ ] TaskController with all methods
  - [ ] Task views (index, create, edit, show)
  - [ ] Form validation
- [ ] Implement Categories
  - [ ] Category model and migration
  - [ ] Category CRUD operations
  - [ ] Link tasks to categories
- [ ] Add search and filtering
- [ ] Implement task status toggling

**Learning Focus:** CRUD, relationships, validation

### Phase 3: Enhancement (Week 3)

- [ ] Create Dashboard
  - [ ] Statistics calculation
  - [ ] Recent activity
  - [ ] Charts/visualizations
- [ ] Add Service Layer
  - [ ] TaskService for business logic
  - [ ] DashboardService for stats
- [ ] Improve UI/UX
  - [ ] Tailwind CSS styling
  - [ ] Alpine.js for interactivity
  - [ ] Toast notifications
- [ ] Add pagination and sorting

**Learning Focus:** Services, clean code, UI polish

### Phase 4: Testing & Polish (Week 4)

- [ ] Write Feature Tests
  - [ ] Task CRUD tests
  - [ ] Authentication tests
  - [ ] Category tests
- [ ] Write Unit Tests
  - [ ] Service tests
  - [ ] Model tests
- [ ] Code documentation
- [ ] Performance optimization
- [ ] Security review
- [ ] Deployment guide

**Learning Focus:** Testing, optimization, production readiness

---

## Understanding the Code

### How a Request Flows

```
1. User visits /tasks
   │
   ▼
2. routes/web.php matches the URL
   Route::get('/tasks', [TaskController::class, 'index'])
   │
   ▼
3. TaskController@index method runs
   public function index() {
       $tasks = Task::with('category')->get();
       return view('tasks.index', compact('tasks'));
   }
   │
   ▼
4. Task model queries database
   SELECT * FROM tasks LEFT JOIN categories...
   │
   ▼
5. Data passed to Blade view
   resources/views/tasks/index.blade.php
   │
   ▼
6. HTML rendered and sent to browser
   │
   ▼
7. User sees the tasks page
```

**This is monolithic architecture in action:**
- Everything happens in ONE application
- Direct function calls between components
- Single database query
- No network calls between services

### Example: Creating a Task

**Route Definition** (`routes/web.php`)
```php
Route::post('/tasks', [TaskController::class, 'store'])->name('tasks.store');
```

**Controller** (`app/Http/Controllers/TaskController.php`)
```php
public function store(StoreTaskRequest $request)
{
    $task = Task::create([
        'title' => $request->title,
        'description' => $request->description,
        'category_id' => $request->category_id,
        'user_id' => auth()->id(),
        'status' => 'pending',
    ]);

    return redirect()
        ->route('tasks.show', $task)
        ->with('success', 'Task created successfully!');
}
```

**Model** (`app/Models/Task.php`)
```php
class Task extends Model
{
    protected $fillable = [
        'title',
        'description',
        'category_id',
        'user_id',
        'status'
    ];

    public function category()
    {
        return $this->belongsTo(Category::class);
    }

    public function user()
    {
        return $this->belongsTo(User::class);
    }
}
```

**View** (`resources/views/tasks/create.blade.php`)
```blade
<form method="POST" action="{{ route('tasks.store') }}">
    @csrf
    <input type="text" name="title" required>
    <textarea name="description"></textarea>
    <select name="category_id">
        @foreach($categories as $category)
            <option value="{{ $category->id }}">{{ $category->name }}</option>
        @endforeach
    </select>
    <button type="submit">Create Task</button>
</form>
```

**Why This is Monolithic:**
1. All code in one project
2. Direct calls between Controller → Model → Database
3. No API calls or microservices
4. Single deployment

---

## Best Practices

### Controller Best Practices

**Good:** Keep controllers thin
```php
class TaskController extends Controller
{
    public function store(StoreTaskRequest $request, TaskService $taskService)
    {
        $task = $taskService->createTask($request->validated());
        return redirect()->route('tasks.show', $task);
    }
}
```

**Bad:** Fat controllers with too much logic
```php
class TaskController extends Controller
{
    public function store(Request $request)
    {
        // Validation
        $validated = $request->validate([...]);

        // Business logic
        if ($validated['priority'] == 'high') {
            // Send notification
            // Log activity
            // Update statistics
        }

        // Database operations
        $task = Task::create($validated);

        // More logic...
    }
}
```

### Service Layer Pattern

**Create services for complex business logic:**

```php
// app/Services/TaskService.php
class TaskService
{
    public function createTask(array $data): Task
    {
        $task = Task::create($data);

        // Business logic here
        $this->sendNotification($task);
        $this->updateStatistics($task->user);

        return $task;
    }

    private function sendNotification(Task $task): void
    {
        // Notification logic
    }
}
```

### Model Best Practices

**Use scopes for common queries:**

```php
class Task extends Model
{
    public function scopeCompleted($query)
    {
        return $query->where('status', 'completed');
    }

    public function scopeForUser($query, User $user)
    {
        return $query->where('user_id', $user->id);
    }
}

// Usage
$tasks = Task::completed()->forUser(auth()->user())->get();
```

### Validation

**Use Form Requests for validation:**

```php
// app/Http/Requests/StoreTaskRequest.php
class StoreTaskRequest extends FormRequest
{
    public function rules(): array
    {
        return [
            'title' => 'required|string|max:255',
            'description' => 'nullable|string',
            'category_id' => 'required|exists:categories,id',
            'priority' => 'in:low,medium,high',
        ];
    }

    public function messages(): array
    {
        return [
            'title.required' => 'Please enter a task title',
            'category_id.exists' => 'Invalid category selected',
        ];
    }
}
```

---

## Testing

### Running Tests

```bash
# Run all tests
php artisan test

# Or use Pest directly
./vendor/bin/pest

# Run specific test file
php artisan test tests/Feature/TaskTest.php

# Run with coverage
php artisan test --coverage
```

### Example Feature Test

```php
// tests/Feature/TaskTest.php
test('user can create a task', function () {
    $user = User::factory()->create();
    $category = Category::factory()->create();

    $this->actingAs($user)
        ->post(route('tasks.store'), [
            'title' => 'Test Task',
            'description' => 'Test Description',
            'category_id' => $category->id,
        ])
        ->assertRedirect()
        ->assertSessionHas('success');

    $this->assertDatabaseHas('tasks', [
        'title' => 'Test Task',
        'user_id' => $user->id,
    ]);
});

test('guest cannot create a task', function () {
    $this->post(route('tasks.store'), [
        'title' => 'Test Task',
    ])
        ->assertRedirect(route('login'));
});
```

### Testing Database

```php
use Illuminate\Foundation\Testing\RefreshDatabase;

uses(RefreshDatabase::class);

test('task belongs to category', function () {
    $category = Category::factory()->create(['name' => 'Work']);
    $task = Task::factory()->create(['category_id' => $category->id]);

    expect($task->category->name)->toBe('Work');
});
```

---

## Deployment

### Production Checklist

- [ ] Set `APP_ENV=production` in `.env`
- [ ] Set `APP_DEBUG=false`
- [ ] Generate new `APP_KEY`
- [ ] Configure proper database
- [ ] Set up queue workers
- [ ] Configure caching
- [ ] Set up proper logging
- [ ] Enable HTTPS
- [ ] Set up backups
- [ ] Configure monitoring

### Deployment Commands

```bash
# Optimize for production
php artisan config:cache
php artisan route:cache
php artisan view:cache

# Build frontend assets
npm run build

# Run migrations
php artisan migrate --force
```

---

## Troubleshooting

### Common Issues

**"Class not found"**
```bash
composer dump-autoload
```

**"SQLSTATE[HY000] [1049] Unknown database"**
- Check `.env` database credentials
- Make sure database exists

**"Mix manifest not found" or Vite errors**
```bash
npm install
npm run dev
```

**"Application key not set"**
```bash
php artisan key:generate
```

**Permission errors**
```bash
chmod -R 775 storage bootstrap/cache
```

---

## Contributing

This is a learning project! Contributions are welcome:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

**Ways to contribute:**
- Fix bugs
- Add features
- Improve documentation
- Add tests
- Share feedback

---

## Resources

### Laravel Documentation
- [Official Laravel Docs](https://laravel.com/docs)
- [Laravel Bootcamp](https://bootcamp.laravel.com/)
- [Laracasts](https://laracasts.com) - Video tutorials

### Testing
- [Pest Documentation](https://pestphp.com/)
- [Laravel Testing Guide](https://laravel.com/docs/testing)

### Architecture Learning
- [Martin Fowler - Monolith First](https://martinfowler.com/bliki/MonolithFirst.html)
- [Laravel Beyond CRUD](https://laravel-beyond-crud.com/)

### Community
- [Laravel Discord](https://discord.gg/laravel)
- [Laravel Forums](https://laracasts.com/discuss)
- [r/laravel](https://reddit.com/r/laravel)

---

## License

This project is open-sourced under the [MIT license](LICENSE).

---

## Summary

**What you've learned:**
- ✅ What monolithic architecture is
- ✅ How Laravel implements this pattern
- ✅ Project structure and organization
- ✅ CRUD operations
- ✅ Database relationships
- ✅ Testing fundamentals

**Next Steps:**
1. Build this project following the roadmap
2. Experiment with the code
3. Add your own features
4. Move to the next architecture pattern

**Remember:** This is a learning journey. Don't rush, ask questions, and enjoy the process!

---

<div align="center">

**Happy Coding! 🚀**

Part of the [Laravel Architecture Learning Hub](../arch)

[Report Issues](https://github.com/your-repo/issues) | [Discussions](https://github.com/your-repo/discussions)

</div>
