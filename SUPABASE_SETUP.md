Supabase Setup Guide

# Supabase Setup Guide

 This project uses [Supabase](<https://supabase.com/>) for its database and Supabase migrations for tracking database changes.

 ## Supabase Project

 **Project Reference:**

```
kdkhbeumhsvsswfkfkdu
```

 The project reference is safe to include in this repository. **Never commit passwords, access tokens, service-role keys, or other secrets.**

---

 ## Initial Setup

 Install the Supabase CLI if it is not already installed.

 From the root directory of this project, link the local project to Supabase:

```
supabase link --project-ref kdkhbeumhsvsswfkfkdu
```

 If the database already contains tables and other schema objects that are not represented in your local migrations, pull the existing schema first:

```
supabase db pull
```

 Review the generated migration before committing it to GitHub.

---

 ## Creating a New Migration

 Whenever you make a database/schema change, create a new migration:

```
supabase migration new new-migration
```

 Replace `new-migration` with a meaningful description.

 For example:

```
supabase migration new add_profiles_table
```

 This creates a SQL file in:

```
supabase/migrations/
```

 Edit the generated `.sql` file and add the required database changes.

 ### Good migration names

 Use names that clearly describe the change:

```
add_profiles_table
add_user_preferences
create_orders_table
add_profile_indexes
update_order_status
```

---

 ## Applying Migrations

 After reviewing a migration, apply pending migrations to the linked Supabase project:

```
supabase db push
```

 Only migrations that have not already been applied will be run.

---

 ## Saving Migrations to GitHub

 Migration files should be committed to Git so that the database schema is version-controlled alongside the application code.

```
git add supabase/migrations
git commit -m "Add database migration"
git push
```

 Do **not** manually edit or delete previously applied migrations unless you understand the consequences. Create a new migration for subsequent database changes.

---

 ## Standard Development Workflow

 For a typical database change:

 ### 1\. Create the migration

```
supabase migration new describe-your-change
```

 ### 2\. Edit the SQL file

 Find the new file under:

```
supabase/migrations/
```

 Add the SQL needed for the change.

 ### 3\. Apply the migration

```
supabase db push
```

 ### 4\. Commit the migration

```
git add supabase/migrations
git commit -m "Describe database change"
git push
```

---

 ## Recommended Repository Structure

 Your repository should look similar to:

```
project/
├── .github/
│   └── workflows/
│       └── supabase-migrations.yml
├── supabase/
│   ├── migrations/
│   │   └── <timestamp>_migration_name.sql
│   └── config.toml
├── SUPABASE_SETUP.md
└── ...
```

---

 ## Optional: Automatic Migrations with GitHub Actions

 If you want GitHub to automatically apply migrations when changes are pushed to `main`, create this separate file:

```
.github/workflows/supabase-migrations.yml
```

 Add:

```
name: Supabase Database Migrations

on:
  push:
    branches:
      - main

jobs:
  migrate:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Setup Supabase CLI
        uses: supabase/setup-cli@v1
        with:
          version: latest

      - name: Link Supabase project
        run: |
          supabase link \
            --project-ref kdkhbeumhsvsswfkfkdu \
            --password "${{ secrets.SUPABASE_DB_PASSWORD }}"
        env:
          SUPABASE_ACCESS_TOKEN: ${{ secrets.SUPABASE_ACCESS_TOKEN }}

      - name: Apply migrations
        run: supabase db push
        env:
          SUPABASE_ACCESS_TOKEN: ${{ secrets.SUPABASE_ACCESS_TOKEN }}
```

 ### GitHub Secrets

 If automatic migrations are enabled, add these secrets to the GitHub repository:

```
SUPABASE_ACCESS_TOKEN
SUPABASE_DB_PASSWORD
```

 Go to:

 **GitHub → Repository → Settings → Secrets and variables → Actions**

 Then select **New repository secret**.

 Never place the actual values of these secrets in this file or anywhere else in the repository.

---

 ## Security

 Never commit:

```
.env
.env.local
Supabase database passwords
Supabase access tokens
Supabase service-role keys
Private API keys
Private credentials
```

 Use environment variables and GitHub Actions Secrets for sensitive credentials.

---

 ## Summary

 The database migration workflow is:

```
supabase migration new describe-your-change
```

 Edit the generated SQL file:

```
supabase/migrations/
```

 Apply it:

```
supabase db push
```

 Commit it:

```
git add supabase/migrations
git commit -m "Add database migration"
git push
```

