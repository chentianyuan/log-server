# Migration `20200426140120-index`

This migration has been generated by 徐帅武 at 4/26/2020, 2:01:20 PM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql

```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration 20200426140013-init..20200426140120-index
--- datamodel.dml
+++ datamodel.dml
@@ -2,9 +2,9 @@
 // learn more about it in the docs: https://pris.ly/d/prisma-schema
 datasource mysql {
   provider = "mysql"
-  url = "***"
+  url      = env("DATABASE_URL")
 }
 generator client {
   provider = "prisma-client-js"
@@ -17,9 +17,9 @@
   content String
   app App @relation(fields: [appId], references: [id])
   appId String
-  // @@index([appId], name: "appId")
+  @@index([appId], name: "appId")
 }
 model Monitor {
   id String @id @default(cuid())
@@ -30,9 +30,9 @@
   createdAt DateTime @default(now())
   app App @relation(fields: [appId], references: [id])
   appId String
-  // @@index([appId], name: "appId")
+  @@index([appId], name: "appId")
 }
 model App {
   id String @id @default(cuid())
```


