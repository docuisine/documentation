# Style Guides

## Contributing Code

Before committing or pushing changes, we aim to follow a set of standards to keep commits and changes easy to understand and meaningful.
These standards are used to enhance communication between fellow contributors who write and read code for the project. Fewer chances of overthinking communication and a higher chance of shipping high quality contributions.

### Commit Guidelines

We follow and extend [this framework](https://github.com/wgtechlabs/clean-commit), we recommend to at least take a glance or skim through the [specification](https://github.com/wgtechlabs/clean-commit/blob/main/SPECIFICATION.md). Basically, we make commits in this format: `{emoji} {type}{(scope)<optional>}: {description}`.

| Emoji | Type       | What it covers                                               |
| :---: | ---------- | ------------------------------------------------------------ |
|  📦   | `new`      | Adding new features, files, or capabilities                  |
|  🔧   | `update`   | Changing existing code, refactoring, improvements, bug fixes |
|  🗑️   | `remove`   | Removing code, files, features, or dependencies              |
|  🔒   | `security` | Security fixes, patches, vulnerability resolutions           |
|  ⚙️   | `setup`    | Project configs, CI/CD, tooling, build systems               |
|  ☕   | `chore`    | Maintenance tasks, dependency updates, housekeeping          |
|  🧪   | `test`     | Adding, updating, or fixing tests                            |
|  📖   | `docs`     | Documentation changes and updates                            |
|  🏷️   | `release`  | Version releases and release preparation                     |

!!! Example "Examples"

    ```
    📦 new: user authentication system
    🛠️ update(api): improve error handling  # with optional scope
    🔒 security(auth): fix jwt token validation bypass
    🗑️ remove(deps): unused axios dependency
    ☕ chore(deps): bump react from 17.0.2 to 18.2.0
    📖 docs: fix typos in contributing guide
    ```

### Conventional Comments

When communicating with fellow contributors, it is recommended to follow this [format](https://conventionalcomments.org/) or communicate so in a similar format that is practical and direct to the point.

## Backend

These are style guides for both Python code and the database schema.

## Project, Folder & File Names

### Rules

- **lowercase**
- **snake_case**
- **nouns for folders**
- **verbs only when it’s an action module**
- **no hyphens**

### Examples

```
app/
├── main.py
├── api/
│   ├── v1/
│   │   ├── routes/
│   │   │   ├── users.py
│   │   │   ├── recipes.py
│   │   │   └── auth.py
│   │   ├── dependencies.py
│   │   └── schemas/
│   │       ├── user.py
│   │       └── recipe.py
├── core/
│   ├── config.py
│   ├── security.py
│   └── logging.py
├── models/
│   ├── user.py
│   ├── recipe.py
│   └── ingredient.py
├── services/
│   ├── user_service.py
│   └── recipe_service.py
├── db/
│   ├── base.py
│   ├── session.py
│   └── migrations/
└── tests/
```

### Avoid

```
UserRoutes.py
recipe-routes.py
Controllers/
```

## Python Class Names

### Use **PascalCase**

- Pydantic models
- SQLAlchemy models
- Service classes
- Exceptions

```python
class User(Base):
    ...

class RecipeCreate(BaseModel):
    ...

class RecipeService:
    ...
```

### Avoid

```python
class user:
class recipe_service:
```

## Function & Method Names

### Use **snake_case**

- Verbs for actions
- Clear, explicit names

```python
def get_user_by_id(user_id: int) -> User:
    ...

def create_recipe(data: RecipeCreate) -> Recipe:
    ...
```

### FastAPI path operations

```python
@router.get("/{recipe_id}")
def read_recipe(recipe_id: int):
    ...
```

## Variable Names

### Rules

- `snake_case`
- Descriptive
- Avoid abbreviations unless common (`id`, `db`, `api`)

```python
user_id: int
recipe_ingredients: list[RecipeIngredient]
db_session: Session
```

### Avoid

```python
x
tmp
usrId
```

## Constants

### Use **UPPER_SNAKE_CASE**

```python
JWT_ALGORITHM = "HS256"
ACCESS_TOKEN_EXPIRE_MINUTES = 30
```

## Database Table Names

- Use **snake_case**

- Use **plural nouns**

- Be consistent

```sql
users
recipes
recipe_ingredients
recipe_steps
categories
stores
shelves
```

This matches:

- PostgreSQL conventions
- SQLAlchemy defaults
- REST naming

### Avoid

```sql
User
RecipeIngredient
recipeIngredients
```

## Database Column Names

### Rules

- `snake_case`
- Descriptive
- No table name prefix
- Avoid reserved words

```sql
id
user_id
created_at
amount_grams
amount_readable
cook_time_sec
```

### Avoid

```sql
userId
recipeID
tbl_user_id
```

## SQLAlchemy Model Naming (Best Practice)

### Class ↔ Table mapping

```python
class Recipe(Base):
    __tablename__ = "recipes"

    id = Column(Integer, primary_key=True)
    user_id = Column(ForeignKey("users.id"))
    title = Column(String)
```

## Pydantic Schema Naming

### Suffix-based clarity

```python
UserBase
UserCreate
UserRead
UserUpdate

RecipeBase
RecipeCreate
RecipeRead
```

## API Route Naming

### REST-style, plural nouns

```http
GET    /api/v1/recipes
POST   /api/v1/recipes
GET    /api/v1/recipes/{id}
PUT    /api/v1/recipes/{id}
DELETE /api/v1/recipes/{id}
```

### Avoid

```
/getRecipe
/create-recipe
```

## Test File Naming (pytest)

```text
test_users.py
test_recipes.py
test_auth.py
```

Test functions:

```python
def test_create_recipe_success():
    ...
```

## Type Hints & Docstrings (Strongly Recommended)

```python
def create_recipe(
    db: Session,
    user_id: int,
    data: RecipeCreate,
) -> Recipe:
    """Create a new recipe for a user."""
```

## Linters & Formatters

### Required

```bash
ruff
black
mypy
```

### Recommended config

```toml
[tool.black]
line-length = 99

[tool.ruff]
select = ["E", "F", "B", "I"]
```

### API response messages

Messages that contain string variable values should be single-quoted, otherwise if numeric use no quotes at all.

String response:

```
Something name 'something' was not found.
```

Numeric response:

```
Somethin ID 1 was not found.
```

### Docstrings

We use the [NumPy style](https://numpydoc.readthedocs.io/en/latest/format.html) for writing docstrigns

## Golden Rule (Very Important)

> **Python names → snake_case** > **Classes → PascalCase** > **DB tables → plural snake_case** > **DB columns → snake_case**
